# QueryCraft 🚀

QueryCraft is a full-stack application for generating SQL queries from natural language and managing database schemas. This repository serves as the central hub for the project, linking the specialized Frontend and Backend environments.

## 🔗 Project Architecture

The project is split into two main repositories:

- **Frontend Repository**: Built with Next.js, handling the user interface and interactive query building.
- **Backend Repository**: Built with Node.js, managing the logic, API endpoints, and database integrations.

## 🛠 Features

### Frontend
- **User Interface**: Intuitive Dashboard
- **Real-time Interaction**: Live query previews
- **Responsive Design**: Optimized for mobile and desktop viewing.

### Backend
- **API Engine**: Robust RESTful API.
- **Data Processing**: Natural Language Processing for SQL conversion using LLM
- **Security**: JWT authentication and secure data handling.

## 🚀 Getting Started

To get a local copy up and running, follow these steps for both components.

### Prerequisites
- Node.js (v18 or higher)

### Installation & Setup

1. **Backend Setup**
   ```bash
   git clone https://github.com/RAIF-KARANI/Query_Craft--Backend.git
   cd Query_Craft--Backend
   npm install
   # Configure your .env file
   npm run dev
   ```

2. **Frontend Setup**
   ```bash
   git clone https://github.com/RAIF-KARANI/Query_Craft--Frontend.git
   cd Query_Craft--Frontend
   npm install
   npm run dev
   ```

## 🧪 Tech Stack

| Layer       | Technologies |
|-------------|--------------|
| Frontend   | Next.js, React, TypeScript, Tailwind CSS, Radix UI |
| Backend    | Node.js, Express, MongoDB/Mongoose, MySQL, PostgreSQL, SQLite, Neo4j |
| Tools      | Git, Postman, Vercel/Heroku |

## 📄 License

This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request to either the Frontend or Backend repositories.
