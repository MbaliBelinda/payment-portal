Access the Application
1. Open your web browser (Chrome, Firefox, or Edge recommended)
2. Navigate to: http://localhost:5173 (when running locally)
3. The application will load automatically

Test Accounts - Use These to Login

Regular User Account:
Email: user@example.com
Password: Password123!
Use this for: Making payments, viewing payment history

Administrator Account:
Email: admin@example.com
Password: AdminPass123!
Use this for: Admin features, user management

Step-by-Step Testing Instructions

1. User Registration & Login

Test Registration:
1. Click "Register" button on homepage
2. Fill in the form:
   - Full Name: John Doe
   - Email: newuser@test.com
   - Password: NewPassword123!
   - Confirm Password: NewPassword123!
3. Click "Register"
4. Expected Result: Success message or redirect to login

Test Registration Errors:
- Try using user@example.com (already exists)
- Try weak password like 123
- Try mismatched passwords
- Expected Result: Clear error messages showing what's wrong

Test Login:
1. Click "Login" button
2. Enter credentials:
   - For user features: user@example.com / Password123!
   - For admin features: admin@example.com / AdminPass123!
3. Click "Login"
4. Expected Result: Redirect to dashboard

Test Login Errors:
- Try wrong password: user@example.com / wrongpassword
- Try non-existent email: nonexistent@test.com / Password123!
- Expected Result: "Invalid credentials" error message

2. Dashboard & Navigation
Test Dashboard Access:
1. After login, you should see your Dashboard
2. Check for:
   - Welcome message with your name
   - Account summary
   - Navigation menu

3. Payment Management
Create a Payment:
1. Click "Create Payment" or "New Payment"
2. Fill in payment details:
   - Recipient Name: Jane Smith
   - Account Number: 123456789
   - Amount: 1000.00
   - Currency: USD
   - Reference: Invoice #123
3. Click "Submit Payment"
4. Expected Result: Success message with payment confirmation

Test Payment Errors:
- Try negative amount: -100
- Try empty required fields
- Try invalid account number format
- Expected Result: Clear validation errors preventing submission

View Payment History:
1. Click "Payments" or "Payment History"
2. View your transaction list
3. Click on any payment to see details
4. Expected Result: Complete payment history with status updates

4. SWIFT International Payments

Send SWIFT Payment:
1. Navigate to "SWIFT Payments" section
2. Fill in international details:
   - SWIFT Code: DEUTDEFF
   - IBAN: DE89370400440532013000
   - Bank Name: Deutsche Bank
   - Beneficiary: Global Corp
   - Amount: 5000.00
   - Currency: EUR
3. Click "Send SWIFT Payment"
4. Expected Result: Transaction reference number and success status

5. Admin Features (Admin Account Only)

Access Admin Dashboard:
1. Login with: admin@example.com / AdminPass123!
2. Click "Admin Dashboard" in navigation
3. Expected Result: Special admin interface with additional options

User Management:
1. In admin dashboard, click "Users"
2. View all registered users
3. Check user activity and roles
4. Expected Result: Complete user list with management options

Security Features to Test

1. Session Protection:
- What to do: Login and check if you can copy session data
- Expected: Cannot access secure cookies via browser
- This proves: Protection against session theft

2. CSRF Protection:
- What to do: Try to submit forms without proper tokens
- Expected: Forms should fail with security errors
- This proves: Protection against cross-site request forgery

3. Input Validation:
- What to do: Try entering <script>alert('xss')</script> in any field
- Expected: Input is blocked or sanitized
- This proves: Protection against malicious scripts

4. Rate Limiting:
- What to do: Rapidly click Login button multiple times
- Expected: After 5-10 attempts, you get temporarily blocked
- This proves: Protection against brute force attacks

5. Authorization:
- What to do: Login as user (user@example.com) and try to access /admin pages
- Expected: Access denied or redirected
- This proves: Proper user role permissions

Common Issues & Solutions

If application won't load:
- Check that backend server is running
- Ensure you're using http://localhost:5173
- Try refreshing the page

If login fails:
- Double-check email/password spelling
- Ensure Caps Lock is off
- Try clearing browser cache

If payments fail:
- Check all required fields are filled
- Ensure amount is positive number
- Verify account number format

If you see security errors:
- This is expected behavior during security testing
- Refresh page and try normal operation
- These errors prove security features are working

For Video Demonstration

When creating your demo video, please show:

Success Cases:
- Successful user registration
- Successful login with both accounts
- Successful payment creation
- Successful SWIFT payment
- Successful admin access

Error Cases:
- Registration validation errors
- Login failure scenarios
- Payment validation errors
- CSRF protection triggering
- Rate limiting in action
- Authorization failures

Security Demonstrations:
- Show security headers in browser dev tools
- Demonstrate XSS prevention
- Show CSRF token requirements
- Prove session protection

Support Information

For testing purposes, remember:
- Use the provided test accounts exactly as shown
- All security errors are good - they prove protections are working
- Test both success and failure scenarios
- The application is designed to be secure first, user-friendly second

Tested Features:
- User authentication (login/register)
- Payment processing and history
- SWIFT international payments
- Admin user management
- Comprehensive security protections
