# Business Management Application

A comprehensive web-based business management system built with Next.js 15+, TypeScript, and shadcn/ui components. This application provides complete client and invoice management capabilities with modern UI design and secure authentication.

## 🚀 Features

### Core Functionality
- **Client Management**: Add, edit, delete, and search clients with complete contact information
- **Invoice Management**: Create, edit, and manage invoices with line items, tax calculations, and status tracking
- **Dashboard Overview**: Summary statistics and recent activity feed
- **User Authentication**: Secure login system with NextAuth.js
- **Export & Notifications**: PDF generation, CSV export, and email functionality

### Technical Features
- **Modern UI**: Clean, responsive design using shadcn/ui components and Tailwind CSS
- **Type Safety**: Full TypeScript implementation with comprehensive type definitions
- **Local Storage**: Client-side data persistence (easily replaceable with database)
- **API Architecture**: RESTful API endpoints with proper error handling
- **Form Validation**: Client-side and server-side validation with react-hook-form and Zod
- **PDF Generation**: Client-side PDF generation using jsPDF
- **Responsive Design**: Mobile-friendly interface that works on all devices

## 🛠️ Technology Stack

- **Framework**: Next.js 15+ with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS with shadcn/ui components
- **Authentication**: NextAuth.js
- **Forms**: React Hook Form with Zod validation
- **PDF Generation**: jsPDF
- **State Management**: React hooks with local storage
- **Icons**: Lucide React (minimal usage)

## 📦 Installation

### Prerequisites
- Node.js 18+
- npm, yarn, pnpm, or bun

### Setup
1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Open [http://localhost:8000](http://localhost:8000) in your browser

## 🔐 Authentication

### Demo Credentials
- **Email**: admin@business.com
- **Password**: admin123

The application uses NextAuth.js with a simple credentials provider. In production, you should:
- Use environment variables for credentials
- Implement proper password hashing
- Add additional security measures

## 📱 Application Structure

### Pages
- `/` - Login page (redirects to dashboard if authenticated)
- `/dashboard` - Main dashboard with statistics and recent activity
- `/clients` - Client list with search and filtering
- `/clients/new` - Add new client form
- `/clients/[id]` - Client details view
- `/clients/[id]/edit` - Edit client form
- `/invoices` - Invoice list with status filtering
- `/invoices/new` - Create new invoice form
- `/invoices/[id]` - Invoice details and actions
- `/invoices/[id]/edit` - Edit invoice form

### API Endpoints

#### Clients
- `GET /api/clients` - List all clients
- `POST /api/clients` - Create new client
- `GET /api/clients/[id]` - Get client details
- `PATCH /api/clients/[id]` - Update client
- `DELETE /api/clients/[id]` - Delete client

#### Invoices
- `GET /api/invoices` - List all invoices
- `POST /api/invoices` - Create new invoice
- `GET /api/invoices/[id]` - Get invoice details
- `PATCH /api/invoices/[id]` - Update invoice
- `DELETE /api/invoices/[id]` - Delete invoice
- `GET /api/invoices/[id]/pdf` - Generate PDF
- `GET /api/invoices/[id]/csv` - Export CSV
- `POST /api/invoices/[id]/send-email` - Send invoice email

#### Authentication
- `POST /api/auth/[...nextauth]` - NextAuth.js endpoints

## 💾 Data Storage

The application currently uses browser localStorage for data persistence. This provides:
- Immediate functionality without external dependencies
- Easy testing and development
- Client-side data management

### Upgrading to Database
To upgrade to a database solution:
1. Replace storage functions in `src/lib/storage.ts`
2. Update API routes to use database queries
3. Add database connection and models
4. Recommended: Supabase, Vercel Postgres, or MongoDB

## 🎨 UI Components

The application uses shadcn/ui components for consistent design:
- **Forms**: Input, Label, Button, Select components
- **Layout**: Card, Table, Badge, Alert components
- **Navigation**: Responsive sidebar and navigation
- **Feedback**: Toast notifications with Sonner

### Design Principles
- Clean, modern aesthetic
- Consistent spacing and typography
- Responsive design for all screen sizes
- Accessible components with proper ARIA labels
- No external icons or images (typography-focused)

## 📊 Features Overview

### Client Management
- Complete CRUD operations
- Search and filter functionality
- Contact information management
- Company details tracking
- Activity history

### Invoice Management
- Dynamic line items with automatic calculations
- Tax calculations per line item
- Multiple currency support
- Status tracking (Draft, Sent, Paid, Overdue)
- Due date management
- Client association

### Dashboard
- Total clients count
- Total invoices count
- Unpaid invoices tracking
- Monthly income calculation
- Recent activity feed

### Export & Communication
- PDF invoice generation
- CSV data export
- Email invoice functionality (demo implementation)
- Print-friendly invoice layouts

## 🔧 Development

### Project Structure
```
src/
├── app/                    # Next.js app router pages
│   ├── api/               # API routes
│   ├── clients/           # Client management pages
│   ├── invoices/          # Invoice management pages
│   ├── dashboard/         # Dashboard page
│   └── login/             # Authentication page
├── components/            # Reusable UI components
│   ├── ui/               # shadcn/ui components
│   ├── Layout.tsx        # Main layout component
│   ├── ClientForm.tsx    # Client form component
│   ├── InvoiceForm.tsx   # Invoice form component
│   └── LineItemRow.tsx   # Invoice line item component
├── lib/                   # Utility functions and types
│   ├── types.ts          # TypeScript type definitions
│   ├── storage.ts        # Data storage utilities
│   ├── auth.ts           # Authentication configuration
│   └── utils.ts          # General utilities
└── hooks/                 # Custom React hooks
```

### Key Files
- `src/lib/types.ts` - All TypeScript interfaces and types
- `src/lib/storage.ts` - Data management functions
- `src/lib/auth.ts` - NextAuth.js configuration
- `src/components/Layout.tsx` - Main application layout
- `src/app/layout.tsx` - Root layout with providers

## 🚀 Production Deployment

### Build for Production
```bash
npm run build
npm start
```

### Environment Variables
For production deployment, set:
```env
NEXTAUTH_SECRET=your-secret-key
NEXTAUTH_URL=https://yourdomain.com
```

### Recommended Upgrades for Production
1. **Database Integration**: Replace localStorage with PostgreSQL/MongoDB
2. **Email Service**: Integrate with SendGrid, Mailgun, or Resend
3. **File Storage**: Use AWS S3 or similar for PDF storage
4. **Authentication**: Add OAuth providers or enterprise SSO
5. **Monitoring**: Add error tracking and analytics
6. **Security**: Implement rate limiting and input sanitization

## 📝 License

This project is built as a demonstration of modern web application development practices using Next.js and TypeScript.

## 🤝 Contributing

The application is designed to be easily extensible. Key areas for enhancement:
- Additional export formats
- Advanced reporting features
- Multi-user support
- Payment integration
- Advanced client management
- Automated invoice reminders

---

**Demo Credentials**: admin@business.com / admin123
