# Go Form Service

## Purpose

The **Go Form Service** addresses a critical need: although students have applied for government loans and been accepted, HELSB lacks sufficient information to create legally binding contracts ensuring loan repayment. To address this, the service collects additional details (such as next of kin and home address) during the screening process.

**Note:** Keep in mind that this is a prototype, so its functionalities are limited compared to a full-scale implementation.

## Client Side

### Pages

1. **Proof of Payment:**

    - Every student (whether returning or first-year) must pay for the screening form.
    - After payment, students receive a transaction ID (receipt number) as proof of payment.
    - Returning students provide additional information, such as their Student Loan Number from the previous year (also serving as proof of identity).
    - **Note:** Receipts are removed from the database after application to prevent reuse.
2. **First-Year Student Form:**

    - This form represents the actual contract between the student and the Loans Board.
    - Detailed form instructions are available in the `bc.md` file on the GitHub page.
    - Upon submission, an automatic Loan Number is generated and added to the student’s record in the database.
    - Successful submission leads to the creation of the student’s record, and they are redirected to the login page.
    - The Loan Number is displayed, with a reminder for the student to keep it safe.
3. **Returning Student Form:**

    - Similar to the first-year form, this form serves as a contract between the student and the Loans Board.
    - Instructions are available in the `bc2.md` file on the GitHub page.
    - When a user authenticates using their receipt and student loan number, the system fetches their existing student record.
    - Details are automatically populated in the frontend form.
    - **Note:** Not all fields should be open for updates; only bank details and guardian information remain editable.

### After Form Submission

- Students are redirected to the login page, where a success message confirms their form submission.
- For first-year students, the new Student Loan Number is displayed, emphasizing the need to keep it secure.

## Admin Dashboard

_This is what is presented to the Loans Board._

The admin dashboard provides an overview of screened students:

- Details of all screened students are displayed.
- Files uploaded by students (e.g., results, acceptance letters) can be downloaded and reviewed.
- The admin confirms students after careful review.
- If a student uploads improper or invalid files, the admin sends an email notifying them of the issue and prompts them to repeat the screening process.
