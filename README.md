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
