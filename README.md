# Leave Reminder Automation Flow
The Leave Reminder Automation Flow is built using Power Automate, Microsoft Forms, and SharePoint to streamline the leave request and notification process. It calculates upcoming leave dates and automatically sends email reminders to employees 7 days before their leave begins. This automation enhances HR efficiency by ensuring timely notifications and data tracking.

---

### Key Features
- **Automated Reminders**: Sends an email reminder to employees 7 days before their leave starts, ensuring timely notifications.
- **SharePoint Data Storage**: Stores employee leave request details such as start and end dates, ensuring all data is easily accessible and secure.
- **Daily Scheduled Checks**: A recurrence trigger that runs the flow daily to check upcoming leave dates.
- **Personalized Notifications**: Employees receive personalized reminder emails based on their submitted leave data.

### Technologies Used
- **Microsoft Forms**: For collecting employee leave request submissions.
- **SharePoint**: Acts as the backend to store leave request data, including employee name, leave dates, and email.
- **Power Automate**: Automates the entire process from form submission to sending the 7-day reminder emails.
- **Outlook**: Sends email notifications reminding employees about their upcoming leave.

---

### How the Leave Reminder Flow Works

1. **Form Submission via Microsoft Forms:**
   - Employees submit their leave requests through a form, including their name, email, leave start date, and leave end date.
   
2. **Data Storage via SharePoint:**
   - The submitted leave details are saved to a SharePoint list, which acts as the database for all leave requests. The list includes fields like:
     - Employee Name
     - Leave Start Date
     - Leave End Date
     - Email Address
   
3. **Daily Scheduled Checks (Recurrence Trigger):**
   - The flow runs every day using a **Recurrence Trigger** that checks for leave start dates that are exactly 7 days away from the current date.

4. **Calculating the Reminder Date:**
   - Power Automate calculates the notification date by subtracting 7 days from the leave start date using the `Get future time` action.

5. **Checking Leave Dates in SharePoint:**
   - The flow retrieves all items from the SharePoint list and filters them to find employees whose leave is starting in exactly 7 days.

6. **Sending Reminder Emails:**
   - Once an employee's leave start date is identified, an email is automatically sent to their email address, reminding them of their upcoming leave. The email is personalized with the employee's name and leave start date.

---

### Customization

- **Reminder Timing**: You can easily adjust the notification time by modifying the formula used to calculate the reminder date (e.g., change it to 3 days instead of 7).
- **Email Templates**: Customize the email content with your organization's branding and additional information such as HR contact details or links to leave policies.

### Future Enhancements
- **Multi-Step Approvals**: Add an approval step to the flow, requiring manager approval before the leave request is finalized.
- **SMS Notifications**: Integrate Twilio or other SMS services to send text reminders to employees in addition to email notifications.
- **Leave Status Tracking**: Build a Power Apps interface that allows employees to track their leave requests and view the approval status directly.
- **App for Leave Requests**: Build a custom Power Apps solution to replace Microsoft Forms for submitting leave requests, offering a more integrated and feature-rich user experience.

### Contributing
Feel free to open a pull request if you'd like to contribute to the project or suggest enhancements. All contributions are welcome!
