# ContactMailer

ContactMailer is a full-stack application for handling contact form submissions and sending emails. It uses Vue.js for the front end and Node.js with Express and Nodemailer for the back end.

## Features

- Simple contact form with fields for name, email, and message.
- Sends an email to a specified address with the form details.
- Uses Nodemailer for email delivery through Gmail.

## Prerequisites

- Node.js and npm
- Vue CLI
- A Gmail account with an app-specific password

## Setup

### Front End (Vue.js)

1. **Clone the repository**:

    ```sh
    git clone https://github.com/catikonur/ContactMailer.git
    cd ContactMailer/frontend
    ```

2. **Install dependencies**:

    ```sh
    npm install
    ```

3. **Run the development server**:

    ```sh
    npm run serve
    ```

### Back End (Node.js)

1. **Navigate to the backend directory**:

    ```sh
    cd ../backend
    ```

2. **Install dependencies**:

    ```sh
    npm install
    ```

3. **Create an app-specific password for your Gmail account**:
    - Enable 2-Step Verification for your Google account.
    - Generate an app-specific password.

4. **Configure the email transporter**:
    Edit `server.js` and replace the email credentials with your Gmail address and app-specific password.

5. **Run the server**:

    ```sh
    node server.js
    ```

## Usage

1. Navigate to `http://localhost:8080` in your browser.
2. Fill out the contact form and submit it.
3. Check your email for the form submission details.

## Dependencies

### Front End

- Vue.js
- Axios

### Back End

- Express
- Nodemailer
- Body-Parser
- CORS
