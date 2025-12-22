# Repository Structure

This document describes the organization of the HR Family Spare Parts inventory management system.

## Directory Layout

```
hrspares/
├── public/                     # Frontend assets (served statically)
│   ├── css/                    # Stylesheets
│   │   └── styles.css          # Main application styles
│   ├── js/                     # Client-side JavaScript
│   │   └── app.js              # Main frontend application logic
│   ├── images/                 # Static images and assets
│   │   ├── logo.png            # Company logo
│   │   └── engine-bg.jpg.jpg   # Background image
│   ├── index.html              # Main application HTML
│   ├── test.html               # Test page for development
│   └── test-login.html         # Login test page
│
├── src/                        # Backend source code
│   ├── database/               # Database related code
│   │   ├── database.js         # PostgreSQL database wrapper
│   │   └── init-postgres.js    # Database initialization & schema
│   ├── config/                 # Configuration files (future)
│   └── routes/                 # API route handlers (future)
│
├── scripts/                    # Utility scripts
│   ├── database/               # Database management scripts
│   │   ├── clear-database.js           # Interactive database reset
│   │   ├── clear-database-auto.js      # Automated database reset
│   │   ├── create-demo-users.js        # Create demo users
│   │   └── create-production-users.js  # Create production users
│   ├── testing/                # Testing and verification scripts
│   │   ├── stress-test.js              # Performance stress test
│   │   ├── stress-test-aggressive.js   # Aggressive stress test
│   │   ├── test-profit-api.js          # Profit calculation tests
│   │   ├── test-reconnection.js        # Database reconnection tests
│   │   ├── test-return-logic.js        # Return logic tests
│   │   ├── test-optional-customer.js   # Optional customer tests
│   │   ├── verify-database.js          # Database verification
│   │   └── verify-profit-analysis.js   # Profit analysis verification
│   └── development/            # Development utilities
│       ├── check-inventory.js          # Check inventory status
│       ├── check-sale.js               # Check sale details
│       ├── check-sale-items.js         # Check sale items
│       ├── debug-sales.js              # Debug sales issues
│       ├── bulk-data-generator.js      # Generate test data
│       ├── create-test-db.js           # Create test database
│       └── modernize-code.js           # Code modernization utility
│
├── tests/                      # Automated tests (Jest)
│   ├── database.test.js        # Database tests
│   ├── init-postgres.test.js   # Initialization tests
│   ├── routes.test.js          # API route tests
│   └── server.test.js          # Server tests
│
├── docs/                       # Documentation (future)
│
├── server.js                   # Main Express server application
├── package.json                # Node.js dependencies and scripts
├── .env.example                # Environment variables template
├── .gitignore                  # Git ignore patterns
├── ecosystem.config.js         # PM2 configuration
├── Procfile                    # Heroku deployment configuration
└── README.md                   # Project documentation
```

## File Organization Principles

### 1. **Public Directory** (`public/`)
All files that are served directly to the client browser:
- HTML files (application UI)
- CSS stylesheets
- Client-side JavaScript
- Images and static assets

### 2. **Source Directory** (`src/`)
Backend application source code:
- Database layer and initialization
- API route handlers (future separation)
- Application configuration (future)

### 3. **Scripts Directory** (`scripts/`)
Organized by purpose:
- **database/**: Database management and seeding
- **testing/**: Performance tests and verification
- **development/**: Development and debugging tools

### 4. **Tests Directory** (`tests/`)
Automated test suites using Jest framework.

## Key Files

### Backend Core
- **server.js**: Main Express application, API routes, middleware
- **src/database/database.js**: PostgreSQL connection wrapper
- **src/database/init-postgres.js**: Database schema and initialization

### Frontend Core
- **public/index.html**: Single-page application HTML
- **public/js/app.js**: Frontend JavaScript (UI logic, API calls)
- **public/css/styles.css**: Application styling

### Configuration
- **.env**: Environment variables (not in git)
- **.env.example**: Template for environment setup
- **ecosystem.config.js**: PM2 process manager config
- **package.json**: Dependencies and npm scripts

## NPM Scripts

### Production
- `npm start` - Start server in production mode
- `npm run dev` - Start server with auto-reload (development)

### Database Management
- `npm run init-postgres` - Initialize PostgreSQL database
- `npm run clear-database` - Interactive database reset
- `npm run clear-database-auto` - Automated database reset
- `npm run create-demo-users` - Create demo users
- `npm run create-production-users` - Create production users

### Testing
- `npm test` - Run all tests with coverage
- `npm run test:watch` - Run tests in watch mode

### Utilities
- `npm run generate-secret` - Generate secure session secret

## Migration Benefits

This new structure provides:

1. **Clear Separation of Concerns**
   - Frontend files isolated in `public/`
   - Backend logic in `src/`
   - Utilities organized by purpose in `scripts/`

2. **Easier Maintenance**
   - Related files grouped together
   - Intuitive navigation
   - Scalable for future growth

3. **Better Developer Experience**
   - Clear file locations
   - Reduced root directory clutter
   - Standard Node.js project structure

4. **Future-Ready**
   - Easy to add new features
   - Room for API route separation
   - Configuration management prepared

## Next Steps for Modularization

Future improvements could include:

1. **API Routes Separation**
   - Extract routes from server.js to `src/routes/`
   - Separate files for inventory, sales, users, etc.

2. **Middleware Separation**
   - Create `src/middleware/` for custom middleware
   - Auth, validation, error handling

3. **Service Layer**
   - Create `src/services/` for business logic
   - Separate from route handlers

4. **Configuration Management**
   - Move config to `src/config/`
   - Environment-specific settings

5. **Documentation**
   - API documentation in `docs/api/`
   - Deployment guides in `docs/deployment/`
