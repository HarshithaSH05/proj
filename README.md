1. foldercreate on deskptop
2. new github repo
3. folder -> cmd
4. git init
5. git branc -M main
6. git add .
7. git commit -m ,,
8. git remote add origin ....
9. echo "#my proj">README.md
10. git add README.md
11. git commit -m "add readme"
12. git push -u origin main
13. git remote -v
14. jenkins(dont build) add repo
15. cmd ->
16. echo 'pipeline { agent any; stages { stage("Checkout") { steps { git branch: "main", url: "https://github.com/username/repo.git", credentialsId: "your-credential-id" } } } }' > Jenkinsfile
17. git add Jenkinsfile
18. git commit -m "Add jenkinsfile"
19. git push origin main
20. vs code->msin.py->
21. def test_exampple():
         assert 1+1==2
22. terminal: mvn run      python -m pytest main .py



7

app.java

package com.example;

public class App {
    public static void main(String[] args) {
        System.out.println("Hello Maven!");
    }
}

pom.xml 

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         https://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>MyProject</artifactId>
    <version>1.0</version>

</project>


type nul>pom.xml
mkdir src\main\java
type nul>src\main\java\app.java
---------------
mvn compile
mvn test
mvn package
mvn install
mvn clean package
git init
git add .
git commit -m ""
--------------
git remote add origin ...
git remote -v
git push -u origin main


describe('XPath Locator Test', () => {
    it('should login using XPath', async () => {

        await browser.url('https://www.saucedemo.com/');

        const username = await $('//input[@id="user-name"]');
        await username.setValue('standard_user');

        const password = await $('//input[@id="password"]');
        await password.setValue('secret_sauce');

        const loginBtn = await $('//input[@id="login-button"]');
        await loginBtn.click();

        await browser.pause(5000);
    });
});


describe('Google search test', () => {
    it('should open google and verify title', async () => {

        await browser.url('https://www.google.com');

        const title = await browser.getTitle();

        console.log(title);

    });
});


Paste this into `index.html`:

`html
<!DOCTYPE html>
<html>
<head>
  <title>Task Manager</title>
  <!-- jQuery CDN -->
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
  <h2>Task Manager</h2>
  <input type="text" id="taskInput" placeholder="Enter a task">
  <button id="addTask">Add Task</button>
  
  <h3>Tasks:</h3>
  <ul id="taskList"></ul>

  <script src="script.js"></script>
</body>
</html>
```

---

 Step 4: Add jQuery Logic
Create a new file in the same folder called `script.js` and paste:

javascript
$(document).ready(function(){
 
  $("#addTask").click(function(){
    let task = $("#taskInput").val();
    if(task){
      $("#taskList").append("<li>" + task + " <button class='remove'>Remove</button></li>");
      $("#taskInput").val(""); // clear input
    }
  });
  
  $(document).on("click", ".remove", function(){
    $(this).parent().remove();
  });

  
  function getTasks(){
    let tasks = [];
    $("#taskList li").each(function(){
      tasks.push($(this).text().replace(" Remove",""));
    });
    return tasks;


  
  $("#taskList").on("DOMSubtreeModified", function(){
    console.log("Current Tasks:", getTasks());
  });
});
