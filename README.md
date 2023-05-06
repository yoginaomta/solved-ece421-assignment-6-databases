Download Link: https://assignmentchef.com/product/solved-ece421-assignment-6-databases
<br>
<strong>Question 1:</strong> Consider the bank application from Lab 5

(https://eclass.srv.ualberta.ca/mod/assign/view.php?id=4077941):

<ul>

 <li>Create a function to return the transaction history for a given user. The function should have the following signature:</li>

</ul>

<em>            fn get_transactions_history(&amp;self, u_name:&amp;str)-&gt;Result&lt;(),UBaseErr&gt; </em>

Using this function, you should be able to view the transaction history for a given user. A sample output should look like:

<em>Matt received $140 from Jim on 12/10/2019 11:34 p.m.              Matt sent $100 from Andrew on 24/11/2019 01:12 p.m. </em>

<ul>

 <li>Edit the pay function, so it checks for the balance of a given user before allowing them to <em>pay</em> money to another user. The function should not allow the user to send money unless they have enough money in their bank account! That is, they must still have a positive balance after the transfer. (Hint: you may utilize the function <em>get_balance</em> in this task).</li>

 <li>Provide the necessary test functions to test your code in a and b.</li>

</ul>

Please upload your submission as a complete Rust project with the name “<strong>Assignment6Question1</strong>”. The project must contain the database file in the <em>data</em> folder.

<strong>Question 2: </strong>Complete your bank project by creating a command-line app for accessing the database. The app should allow the user to send commands as arguments. Then, the app must be able to interpret these arguments and interact with the user properly.

Here are a set of arguments that the app must be able to work with:

<ul>

 <li><strong>new: </strong>This is a command to create a new user, the second, and the third arguments, in this case, should provide the username and password. If the user forgot to provide the necessary arguments, the app must prompt him/her to complete the command with whatever needed.</li>

 <li><strong>transfer</strong>: This is a command to send money from one user <em>(from_user)</em> to another user <em>(to_user)</em>. Please note that this function requires providing the password of the <em>from_user</em>. Therefore, the app must ask the user to enter his password to complete the payment operation.</li>

 <li><strong>balance</strong>: This is a command to show the balance of a given user. Again, this is a command that requires the user to enter his password first to be able to check his balance.</li>

</ul>

Here is a sample of what should the program look like. Please, note that the user input is highlighted in boldface.

<table width="640">

 <tbody>

  <tr>

   <td width="640"><strong># cargo run — new matt mattpw </strong>Adding user matt with password mattpw… Operation done successfully!<strong># cargo run transfer — steve matt 150 </strong>Please input your password: stevepwSending money from steve to matt… Operation done successfully!<strong>Cargo run — balance matt </strong></td>

  </tr>

 </tbody>

</table>

Please input your password:

mattpw

Balance is $100

Operation done successfully!

Please upload your submission as a complete Rust project with the name “<strong>Assignment6Question2</strong>”. The project must contain the database file in the <em>data</em> folder.

<strong>Question 3: </strong>You have been using bcrypt to encrypt and validate the user password. However, bycrypt is getting old. Malicious users can now successfully attack bcypt using massive concurrent attacks. Hence, best practice is to use argon2 instead <a href="https://docs.rs/rust-argon2/0.5.1/argon2/">(</a><a href="https://docs.rs/rust-argon2/0.5.1/argon2/">https://docs.rs/rust</a><a href="https://docs.rs/rust-argon2/0.5.1/argon2/">–</a><a href="https://docs.rs/rust-argon2/0.5.1/argon2/">argon2/0.5.1/argon2/</a><a href="https://docs.rs/rust-argon2/0.5.1/argon2/">)</a>. Rewrite the code to follow best practices


