# Better Auth Playground

A comprehensive learning playground for implementing **Better Auth** with Next.js, PostgreSQL, Drizzle ORM, and Docker. This project demonstrates all authentication features and use cases provided by Better Auth.

## 🚀 Tech Stack

- **Framework**: Next.js 14+ (App Router)
- **Database**: PostgreSQL (Docker)
- **ORM**: Drizzle ORM
- **Authentication**: Better Auth
- **Containerization**: Docker & Docker Compose
- **TypeScript**: Full type safety

## 📁 Project Structure

```
better-auth-playground/
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   └── auth/
│   │   ├── auth/
│   │   │   ├── sign-in/
│   │   │   ├── sign-up/
│   │   │   ├── forgot-password/
│   │   │   └── verify-email/
│   │   ├── dashboard/
│   │   ├── profile/
│   │   └── admin/
│   ├── components/
│   │   ├── auth/
│   │   ├── ui/
│   │   └── forms/
│   ├── lib/
│   │   ├── auth.ts
│   │   ├── db.ts
│   │   └── utils.ts
│   └── types/
├── drizzle/
│   ├── migrations/
│   └── schema.ts
├── docker-compose.yml
├── drizzle.config.ts
└── README.md
```

## 🔧 Quick Start

### Prerequisites

- Node.js 18+
- Docker & Docker Compose
- pnpm/npm/yarn

### Installation

1. **Clone and install dependencies**

   ```bash
   git clone <your-repo>
   cd better-auth-playground
   npm install
   ```

2. **Start PostgreSQL with Docker**

   ```bash
   docker-compose up -d
   ```

3. **Set up environment variables**

   ```bash
   cp .env.example .env.local
   ```

   Fill in your `.env.local`:

   ```env
   DATABASE_URL="postgresql://postgres:password@localhost:5432/better_auth_db"
   BETTER_AUTH_SECRET="your-secret-key-here"
   BETTER_AUTH_URL="http://localhost:3000"

   # OAuth Providers (optional)
   GOOGLE_CLIENT_ID=""
   GOOGLE_CLIENT_SECRET=""
   GITHUB_CLIENT_ID=""
   GITHUB_CLIENT_SECRET=""

   # Email Provider (optional)
   SMTP_HOST=""
   SMTP_PORT=""
   SMTP_USER=""
   SMTP_PASS=""
   ```

4. **Run database migrations**

   ```bash
   npm run db:migrate
   ```

5. **Start development server**
   ```bash
   npm run dev
   ```

## 📋 Implementation Roadmap

### ✅ Phase 1: Basic Setup

- [ ] Project initialization with Next.js
- [ ] Docker PostgreSQL setup
- [ ] Drizzle ORM configuration
- [ ] Basic Better Auth setup
- [ ] Database schema design

### 🔐 Phase 2: Core Authentication

#### Email/Password Authentication

- [ ] **Sign Up Flow**
  - [ ] User registration form
  - [ ] Email verification
  - [ ] Password strength validation
  - [ ] Username availability check
- [ ] **Sign In Flow**

  - [ ] Login form with email/username
  - [ ] Remember me functionality
  - [ ] Rate limiting implementation
  - [ ] Account lockout after failed attempts

- [ ] **Password Management**
  - [ ] Forgot password flow
  - [ ] Password reset via email
  - [ ] Password change in profile
  - [ ] Password history prevention

#### Session Management

- [ ] **Session Configuration**

  - [ ] Session duration settings
  - [ ] Refresh token implementation
  - [ ] Session invalidation
  - [ ] Multiple device sessions

- [ ] **Security Features**
  - [ ] CSRF protection
  - [ ] Session hijacking prevention
  - [ ] Concurrent session limits
  - [ ] Device fingerprinting

### 🌐 Phase 3: Social Authentication (OAuth)

#### Provider Integration

- [ ] **Google OAuth**

  - [ ] Setup Google Cloud Console
  - [ ] Implement Google sign-in
  - [ ] Handle Google profile data
  - [ ] Account linking

- [ ] **GitHub OAuth**

  - [ ] Setup GitHub OAuth App
  - [ ] Implement GitHub sign-in
  - [ ] Handle GitHub profile data
  - [ ] Repository access (optional)

- [ ] **Additional Providers**
  - [ ] Discord integration
  - [ ] Twitter/X integration
  - [ ] Microsoft integration
  - [ ] Apple integration

#### Account Linking

- [ ] **Multi-Provider Accounts**
  - [ ] Link social accounts to existing users
  - [ ] Unlink social accounts
  - [ ] Primary account selection
  - [ ] Conflict resolution

### 👤 Phase 4: User Management

#### Profile Management

- [ ] **User Profile**

  - [ ] Profile information display
  - [ ] Profile editing form
  - [ ] Avatar upload and management
  - [ ] Profile visibility settings

- [ ] **Account Settings**
  - [ ] Email change with verification
  - [ ] Username change
  - [ ] Account deletion
  - [ ] Data export (GDPR compliance)

#### User Verification

- [ ] **Email Verification**

  - [ ] Email verification on signup
  - [ ] Re-send verification email
  - [ ] Email change verification
  - [ ] Verification status display

- [ ] **Phone Verification** (if supported)
  - [ ] SMS verification setup
  - [ ] Phone number verification
  - [ ] Two-factor authentication via SMS

### 🔒 Phase 5: Advanced Security

#### Two-Factor Authentication (2FA)

- [ ] **TOTP Implementation**

  - [ ] QR code generation
  - [ ] TOTP setup flow
  - [ ] Backup codes generation
  - [ ] 2FA verification during login

- [ ] **Recovery Options**
  - [ ] Backup codes usage
  - [ ] 2FA reset via email
  - [ ] Account recovery flow
  - [ ] Emergency access codes

#### Security Monitoring

- [ ] **Login Analytics**

  - [ ] Login history tracking
  - [ ] Suspicious activity detection
  - [ ] Geographic login tracking
  - [ ] Device management

- [ ] **Security Notifications**
  - [ ] New device login alerts
  - [ ] Password change notifications
  - [ ] Suspicious activity alerts
  - [ ] Account changes notifications

### 👥 Phase 6: Role-Based Access Control (RBAC)

#### Roles and Permissions

- [ ] **Role Management**

  - [ ] Define user roles (admin, user, moderator)
  - [ ] Role assignment interface
  - [ ] Permission-based access control
  - [ ] Dynamic role checking

- [ ] **Protected Routes**
  - [ ] Admin-only pages
  - [ ] Role-based navigation
  - [ ] API route protection
  - [ ] Middleware implementation

#### Organization Support

- [ ] **Multi-Tenant Features**
  - [ ] Organization creation
  - [ ] User invitations
  - [ ] Organization roles
  - [ ] Team management

### 📧 Phase 7: Email Integration

#### Email Templates

- [ ] **Transactional Emails**

  - [ ] Welcome email template
  - [ ] Email verification template
  - [ ] Password reset template
  - [ ] Security notification templates

- [ ] **Email Customization**
  - [ ] Branded email templates
  - [ ] Multi-language support
  - [ ] Email preferences
  - [ ] Unsubscribe handling

### 🛡️ Phase 8: Security Hardening

#### Advanced Security

- [ ] **Rate Limiting**

  - [ ] Login attempt limiting
  - [ ] API rate limiting
  - [ ] IP-based restrictions
  - [ ] Progressive delays

- [ ] **Security Headers**
  - [ ] Content Security Policy
  - [ ] HSTS implementation
  - [ ] X-Frame-Options
  - [ ] Security middleware

#### Compliance

- [ ] **GDPR Compliance**
  - [ ] Data processing consent
  - [ ] Right to be forgotten
  - [ ] Data portability
  - [ ] Privacy policy integration

### 🧪 Phase 9: Testing & Documentation

#### Testing Implementation

- [ ] **Unit Tests**

  - [ ] Authentication flow tests
  - [ ] API endpoint tests
  - [ ] Utility function tests
  - [ ] Database operation tests

- [ ] **Integration Tests**
  - [ ] End-to-end auth flows
  - [ ] OAuth integration tests
  - [ ] Email delivery tests
  - [ ] Session management tests

#### Documentation

- [ ] **API Documentation**

  - [ ] Authentication endpoints
  - [ ] Error handling guide
  - [ ] Integration examples
  - [ ] SDK usage examples

- [ ] **User Guides**
  - [ ] Setup instructions
  - [ ] Configuration guide
  - [ ] Troubleshooting guide
  - [ ] Best practices document

### 🚀 Phase 10: Production Readiness

#### Performance Optimization

- [ ] **Caching Strategy**

  - [ ] Session caching
  - [ ] User data caching
  - [ ] OAuth token caching
  - [ ] Database query optimization

- [ ] **Monitoring & Logging**
  - [ ] Authentication metrics
  - [ ] Error tracking
  - [ ] Performance monitoring
  - [ ] Security event logging

#### Deployment

- [ ] **Production Setup**
  - [ ] Environment configuration
  - [ ] Database migration strategy
  - [ ] SSL/TLS configuration
  - [ ] Container orchestration

## 🔧 Available Scripts

```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server

# Database
npm run db:generate  # Generate Drizzle migrations
npm run db:migrate   # Run database migrations
npm run db:push      # Push schema changes
npm run db:studio    # Open Drizzle Studio

# Docker
docker-compose up -d    # Start PostgreSQL
docker-compose down     # Stop all services
docker-compose logs     # View logs

# Testing
npm run test         # Run unit tests
npm run test:e2e     # Run e2e tests
npm run test:watch   # Run tests in watch mode
```

## 📚 Learning Resources

### Better Auth Documentation

- [Official Better Auth Docs](https://better-auth.com)
- [Better Auth GitHub](https://github.com/better-auth/better-auth)
- [Authentication Best Practices](https://auth0.com/blog/authentication-best-practices/)

### Related Technologies

- [Next.js App Router](https://nextjs.org/docs/app)
- [Drizzle ORM](https://orm.drizzle.team/)
- [PostgreSQL](https://www.postgresql.org/docs/)
- [Docker](https://docs.docker.com/)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔍 Project Goals

This playground aims to:

- Demonstrate all Better Auth capabilities
- Provide real-world implementation examples
- Serve as a reference for production applications
- Explore advanced authentication patterns
- Test security best practices

## 📞 Support

If you have questions or need help:

- Check the [Issues](../../issues) for common problems
- Review the [Better Auth Discord](https://discord.gg/better-auth)
- Read the documentation thoroughly
- Create a new issue with detailed information

---

**Happy coding! 🎉**
