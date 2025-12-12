![Sinatra ActiveRecord Application](sinatra-active-record.webp)

# Sinatra ActiveRecord Todo Application

A beautiful full-stack web application built with traditional Ruby on the backend and modern React on the frontend. This application demonstrates a secure, well-structured todo management system using **Sinatra** as the web framework and **ActiveRecord** as the ORM, following time-tested Ruby conventions and best practices.

## 🎯 Overview

This is a comprehensive todo management application that allows users to create, organize, and track their tasks. Built with a focus on clean, maintainable code using Ruby's elegant syntax and ActiveRecord's powerful database abstraction layer. The application follows traditional secure development practices with plain, readable Ruby code—no magic, just solid engineering.

## 🏗️ Architecture

### Backend (Sinatra + ActiveRecord)
- **Framework**: Sinatra 2.1 with modular application structure
- **ORM**: ActiveRecord 6.1 for database operations
- **Database**: SQLite3
- **Server**: Thin web server
- **API**: RESTful JSON API with namespaced routes (`/api`)
- **Security**: CORS enabled, input validation, secure password handling

### Frontend (React)
- **Framework**: React 17
- **UI Library**: React Bootstrap 5
- **Styling**: Bootstrap 5.1.3
- **Build Tool**: Create React App

## 📋 Features

- ✅ **Todo Management**: Create, read, update, and delete todos
- 👤 **User Management**: User authentication and profile management
- 📁 **Categories**: Organize todos by categories
- 📊 **Status Tracking**: Track todo progress (In Progress, Done)
- 🔍 **Filtering**: Filter todos by time period (Today, Week, Month)
- 📈 **Progress View**: View todos in progress and completed tasks
- 🎨 **Modern UI**: Beautiful, responsive interface built with React Bootstrap

## 🗄️ Database Schema

The application uses four main models with the following relationships:

- **Users** - User accounts with authentication
- **Todos** - Task items belonging to users
- **Categories** - Organization categories for todos
- **Statuses** - Progress tracking for todos

**Relationships**:
- User `has_many` Todos
- Todo `belongs_to` User and Category
- Todo `has_one` Status
- User `has_many` Categories through Todos

## 🚀 Getting Started

### Prerequisites

- Ruby 2.7+ (check with `ruby -v`)
- Bundler gem (`gem install bundler`)
- Node.js 14+ and npm (check with `node -v` and `npm -v`)

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install Ruby dependencies:
```bash
bundle install
```

3. Set up the database:
```bash
bundle exec rake db:create
bundle exec rake db:migrate
bundle exec rake db:seed
```

4. Start the Sinatra server:
```bash
bundle exec rerun 'rackup config.ru'
```

The API will be available at `http://localhost:9292`

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install Node dependencies:
```bash
npm install
```

3. Start the React development server:
```bash
npm start
```

The frontend will be available at `http://localhost:3000`

## 📡 API Endpoints

### Todos
- `GET /api/todo/all` - Get all todos
- `GET /api/todo/:id` - Get a specific todo
- `POST /api/todo/new` - Create a new todo
- `PATCH /api/todo/:id` - Update a todo
- `DELETE /api/todo/:id` - Delete a todo
- `GET /api/todo/progress` - Get todos in progress
- `GET /api/todo/completed` - Get completed todos
- `GET /api/todo/today` - Get today's todos
- `GET /api/todo/week` - Get this week's todos
- `GET /api/todo/month` - Get this month's todos
- `PATCH /api/todo/status/:id` - Update todo status

### Users
- User management endpoints available via `UsersController`

### Categories
- Category management endpoints available via `CategoriesController`

### Statuses
- Status management endpoints available via `StatusesController`

## 🛠️ Technology Stack

### Backend Dependencies
- `sinatra` (~> 2.1) - Web framework
- `sinatra-contrib` (~> 2.1) - Sinatra extensions
- `sinatra-activerecord` (~> 2.0) - ActiveRecord integration
- `activerecord` (~> 6.1) - ORM framework
- `sqlite3` (~> 1.4) - Database adapter
- `thin` (~> 1.8) - Web server
- `rack-cors` (~> 1.1) - CORS middleware
- `rack-contrib` (~> 2.3) - Rack middleware
- `rake` (~> 13.0) - Task runner
- `faker` - Data generation for seeding

### Frontend Dependencies
- `react` (^17.0.2) - UI library
- `react-dom` (^17.0.2) - React DOM renderer
- `react-bootstrap` (^2.1.0) - Bootstrap components
- `bootstrap` (^5.1.3) - CSS framework
- `react-scripts` (5.0.0) - Build tooling

## 🔒 Security Features

- Input validation using ActiveRecord validations
- Email uniqueness validation
- Password length requirements (5-20 characters)
- Field normalization (trimming, case handling)
- CORS configuration for secure cross-origin requests
- SQL injection protection via ActiveRecord parameterized queries

## 📁 Project Structure

```
sinatra-active-record/
├── backend/
│   ├── app/
│   │   ├── controllers/     # Sinatra controllers
│   │   └── models/           # ActiveRecord models
│   ├── config/              # Application configuration
│   ├── db/
│   │   ├── migrate/         # Database migrations
│   │   ├── schema.rb        # Database schema
│   │   └── seeds.rb         # Seed data
│   ├── Gemfile              # Ruby dependencies
│   └── config.ru            # Rack configuration
├── frontend/
│   ├── src/
│   │   ├── components/      # React components
│   │   ├── layout/          # Layout components
│   │   ├── services/        # Service providers
│   │   └── App.js           # Main app component
│   ├── public/              # Static assets
│   └── package.json         # Node dependencies
└── README.md
```

## 🧪 Development

### Running Tests

Backend tests (if configured):
```bash
cd backend
bundle exec rspec
```

Frontend tests:
```bash
cd frontend
npm test
```

### Database Migrations

Create a new migration:
```bash
cd backend
bundle exec rake db:create_migration NAME=migration_name
```

Run migrations:
```bash
bundle exec rake db:migrate
```

Rollback migrations:
```bash
bundle exec rake db:rollback
```

## 📝 Code Style

This application follows Ruby best practices:
- Clean, readable code without unnecessary abstractions
- Traditional MVC pattern
- Explicit validations and callbacks
- Well-structured ActiveRecord associations
- RESTful API design

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

Built with love using:
- Sinatra - The elegant web framework
- ActiveRecord - The powerful ORM
- React - The modern UI library
- Ruby - The beautiful programming language

---

**Note**: This application demonstrates traditional Ruby development practices with Sinatra and ActiveRecord, showcasing how clean, secure, and maintainable applications can be built using plain Ruby code without heavy frameworks.

