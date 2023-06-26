# Security Challenges

**1. Secure Password Generator**

**Question**: Write a function `generate_password(length, complexity)` that generates a secure password of a given length and complexity. The complexity parameter can have three levels - 1, 2, and 3. If complexity is 1, the password should only contain lower case letters. If complexity is 2, the password should contain lower and upper case letters. If complexity is 3, the password should contain lower case, upper case letters and digits.

**Constraints**:
* Length of the password should be between 8 and 64.
* Complexity can only be 1, 2, or 3.

**Test Cases**:
```python
assert re.match('[^a-z]', generate_password(32, 1)) == None
assert re.match('[^a-zA-Z]', generate_password(32, 2)) == None
assert re.match('[^a-zA-Z0-9]', generate_password(32, 3)) == None
```

**2. Secure Data Transmission**

**Question**: Implement a pair of functions `encrypt(message, key)` and `decrypt(ciphertext, key)` for a basic encryption and decryption system using a provided key. Use a simple Caesar cipher for the task.

**Constraints**:
* Message will be a string with alphanumeric characters.
* Key will be an integer between 1 and 25.

**Test Cases**:
```python
assert encrypt('AttackAtDawn123', 23) == 'XqqxzhXqAxtk123'
assert decrypt('XqqxzhXqAxtk123', 23) == 'AttackAtDawn123'
```

**3. SQL Injection Prevention**

**Question**: Write a function `is_safe_sql(query)` that checks if a given SQL query is safe from SQL injection attacks. The function should return True if the query is safe, and False if it's not.

**Constraints**:
* The query will be a string, simulating a simple SQL SELECT statement on a users table.
* A query will be considered unsafe if it contains characters like `'`, `"`, `--`, `;`.

**Test Cases**:
```python
assert is_safe_sql("SELECT * FROM users WHERE id = 1") == True
assert is_safe_sql("SELECT * FROM users WHERE name = 'John'; DROP TABLE users;") == False
```

**4. XSS (Cross Site Scripting) Attack Prevention**

**Question**: Write a function `sanitize_html(html)` that removes potential XSS attacks from a given HTML string.

**Constraints**:
* The input will be a string, simulating a simple HTML content.
* An HTML will be considered as potential XSS attack if it contains `<script>` tag.

**Test Cases**:
```python
assert sanitize_html("<h1>Hello World</h1>") == "<h1>Hello World</h1>"
assert sanitize_html("<h1>Hello <script>alert('XSS Attack');</script> World</h1>") == "<h1>Hello World</h1>"
```

**5. Two-factor Authentication**

**Question**: Write a function `generate_otp(length)` to generate a One-Time Password (OTP) for two-factor authentication, and another function `verify_otp(generated_otp, entered_otp)` to verify the OTP entered by a user.

**Constraints**:
* OTP length should be between 4 to 6.
* Both generated_otp and entered_otp will be strings of digits.

**Test Cases**:
```python
otp = generate_otp(4)
assert verify_otp(otp, otp) == True
assert verify_otp(otp, "1234") == False
```
