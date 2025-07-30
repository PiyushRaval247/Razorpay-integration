# Student Registration System with Razorpay Payment

A complete student registration system with Razorpay payment gateway integration. Built with React, Tailwind CSS, Express.js, and MongoDB.

## Features

- 📝 Complete student registration form
- 💳 Razorpay payment integration (₹500 registration fee)
- 🎨 Modern UI with Tailwind CSS
- 📱 Responsive design
- 🔒 Payment verification and security
- 📊 Student data management
- 🗄️ MongoDB database storage

## Project Structure

```
RazorPay/
├── frontend/          # React application
│   ├── src/
│   │   ├── App.js     # Main application component
│   │   └── index.css  # Tailwind CSS styles
│   └── public/
│       └── index.html # HTML template with Razorpay script
└── backend/           # Express.js server
    ├── server.js      # Main server file
    └── package.json   # Backend dependencies
```

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)
- Razorpay account and API keys

## Setup Instructions

### 1. Clone and Install Dependencies

```bash
# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

### 2. Environment Configuration

Create a `.env` file in the backend directory:

```env
MONGODB_URI=mongodb://localhost:27017/student_registration
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
PORT=5000
```

### 3. Razorpay Setup

1. Sign up for a Razorpay account at [razorpay.com](https://razorpay.com)
2. Get your API keys from the Razorpay Dashboard
3. Replace `your_razorpay_key_id` and `your_razorpay_key_secret` in the `.env` file

### 4. MongoDB Setup

#### Option A: Local MongoDB
1. Install MongoDB locally
2. Start MongoDB service
3. The application will automatically create the database

#### Option B: MongoDB Atlas
1. Create a free account at [mongodb.com](https://mongodb.com)
2. Create a new cluster
3. Get your connection string
4. Replace the `MONGODB_URI` in the `.env` file

### 5. Running the Application

#### Start Backend Server
```bash
cd backend
npm run dev
```

The backend will start on `http://localhost:5000`

#### Start Frontend Application
```bash
cd frontend
npm start
```

The frontend will start on `http://localhost:3000`

## API Endpoints

### Backend API Routes

- `POST /api/students` - Register a new student
- `POST /api/create-order` - Create Razorpay payment order
- `POST /api/verify-payment` - Verify payment signature
- `GET /api/students` - Get all students
- `GET /api/students/:studentId` - Get student by ID
- `GET /api/health` - Health check endpoint

## Usage

1. **Student Registration**: Fill out the complete registration form with personal details
2. **Payment**: After successful registration, proceed to payment (₹500)
3. **Payment Gateway**: Complete payment through Razorpay
4. **Confirmation**: Receive confirmation of successful registration and payment

## Payment Flow

1. Student fills registration form
2. Backend creates student record and generates Student ID
3. Frontend requests payment order from backend
4. Backend creates Razorpay order and returns payment details
5. Frontend opens Razorpay payment modal
6. After payment, backend verifies payment signature
7. Student record is updated with payment status

## Technologies Used

### Frontend
- React.js
- Tailwind CSS
- Axios for API calls
- Razorpay Checkout

### Backend
- Express.js
- MongoDB with Mongoose
- Razorpay SDK
- CORS for cross-origin requests
- Crypto for payment verification

## Security Features

- Payment signature verification
- Input validation
- CORS protection
- Environment variable configuration
- Secure payment processing

## Development

### Frontend Development
```bash
cd frontend
npm start
```

### Backend Development
```bash
cd backend
npm run dev
```

### Building for Production
```bash
# Frontend
cd frontend
npm run build

# Backend
cd backend
npm start
```

## Troubleshooting

1. **MongoDB Connection Error**: Ensure MongoDB is running and connection string is correct
2. **Razorpay Payment Error**: Verify API keys are correct and account is active
3. **CORS Error**: Backend CORS is configured for development, adjust for production
4. **Port Already in Use**: Change PORT in .env file or kill existing process

## License

This project is for educational purposes. Please ensure compliance with Razorpay's terms of service for production use.

## Support

For issues and questions:
1. Check the console for error messages
2. Verify all environment variables are set correctly
3. Ensure all dependencies are installed
4. Check MongoDB connection status 