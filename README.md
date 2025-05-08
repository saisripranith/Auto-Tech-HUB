# Auto Tech-HUB Backend

This is the backend server for the Auto Tech-HUB website, built with Node.js, Express, and MongoDB.

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- Razorpay account
- Gmail account for email notifications

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/autotech-hub
   JWT_SECRET=your-super-secret-jwt-key
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-email-password
   ADMIN_EMAIL=admin@autotech-hub.com
   RAZORPAY_KEY_ID=your-razorpay-key-id
   RAZORPAY_KEY_SECRET=your-razorpay-key-secret
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

## API Endpoints

### Authentication
- POST `/api/auth/register` - Register new user
- POST `/api/auth/login` - Login user

### Products
- GET `/api/products` - Get all products
- GET `/api/products/:id` - Get single product
- POST `/api/products` - Create new product (admin only)
- PUT `/api/products/:id` - Update product (admin only)
- DELETE `/api/products/:id` - Delete product (admin only)
- POST `/api/products/:id/reviews` - Add review to product

### Contact
- POST `/api/contact` - Submit contact form
- GET `/api/contact` - Get all contact submissions (admin only)
- PUT `/api/contact/:id` - Update contact submission status (admin only)

### Payments
- POST `/api/payments/create-order` - Create Razorpay order
- POST `/api/payments/verify` - Verify payment
- GET `/api/payments/:payment_id` - Get payment details
- POST `/api/payments/:payment_id/refund` - Refund payment

## Security

- All routes except registration and login require authentication
- Admin routes are protected with role-based access control
- Passwords are hashed using bcrypt
- JWT tokens are used for authentication
- Environment variables are used for sensitive data

## Error Handling

The API uses a consistent error response format:
```json
{
  "message": "Error message",
  "error": "Detailed error information (in development)"
}
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request 