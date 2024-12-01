# CaseCobra - Custom Phone Case Designer

A modern e-commerce platform for designing and ordering custom phone cases. Users can upload their images, customize case designs, and order high-quality phone cases with their personalized artwork.

## Features

- **Custom Case Designer**: Interactive tool for uploading and positioning images on phone cases
- **Multiple Phone Models**: Support for various iPhone models (iPhone X through iPhone 15)
- **Case Customization**:
  - Multiple materials (silicone, polycarbonate)
  - Various finishes (smooth, textured)
  - Color options (black, blue, rose)
- **Real-time Preview**: Live visualization of your custom case design
- **Secure Checkout**: Integrated with Stripe for secure payments
- **Order Management**: Track orders from payment to shipment
- **User Authentication**: Secure login via Kinde Auth
- **Image Processing**: Advanced image handling with sharp and uploadthing
- **Responsive Design**: Seamless experience across all devices

## Tech Stack

### Frontend
- **Framework**: Next.js 14 with React 18
- **Styling**: 
  - Tailwind CSS for responsive design
  - Radix UI for accessible components
  - Framer Motion for animations
- **State Management**: TanStack Query
- **Image Handling**: 
  - Sharp for image processing
  - UploadThing for file uploads
  - React Dropzone for drag-and-drop

### Backend
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: Kinde Auth
- **Payment Processing**: Stripe
- **Email**: Resend for transactional emails
- **Image Storage**: UploadThing

## Getting Started

1. Clone the repository
2. Install dependencies:
```bash
pnpm install
```

3. Set up environment variables:
```env
DATABASE_URL="your-postgresql-url"
KINDE_CLIENT_ID="your-kinde-client-id"
KINDE_CLIENT_SECRET="your-kinde-client-secret"
KINDE_ISSUER_URL="your-kinde-issuer-url"
KINDE_SITE_URL="your-site-url"
KINDE_POST_LOGIN_REDIRECT_URL="your-redirect-url"
KINDE_POST_LOGOUT_REDIRECT_URL="your-logout-redirect-url"
UPLOADTHING_SECRET="your-uploadthing-secret"
UPLOADTHING_APP_ID="your-uploadthing-app-id"
STRIPE_SECRET_KEY="your-stripe-secret-key"
STRIPE_WEBHOOK_SECRET="your-stripe-webhook-secret"
RESEND_API_KEY="your-resend-api-key"
```

4. Initialize the database:
```bash
pnpm prisma generate
pnpm prisma db push
```

5. Run the development server:
```bash
pnpm dev
```

Visit [http://localhost:3000](http://localhost:3000) to see the application.

## Project Structure

- `/src/app` - Next.js app router pages and API routes
- `/src/components` - Reusable UI components
  - `/ui` - Base UI components
  - `/configure` - Case customization components
- `/src/lib` - Utility functions and configurations
- `/prisma` - Database schema and migrations
- `/public` - Static assets

## Database Schema

The application uses a relational database with the following main entities:
- **Configuration**: Case design settings (size, image, color, model)
- **User**: Customer information and authentication
- **Order**: Purchase details and status
- **ShippingAddress/BillingAddress**: Customer delivery information

## Development

Built with Next.js 14 best practices:
- Server Components for optimal performance
- API Routes for backend functionality
- Prisma for type-safe database queries
- TanStack Query for efficient data fetching
- Stripe integration for secure payments

## Deployment

The application is optimized for deployment on Vercel with:
- Edge Functions support
- Image optimization
- Automatic HTTPS
- Serverless PostgreSQL database support
