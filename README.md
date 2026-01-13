# 💰 Splitty - Collaborative Expense Tracker

A full-stack expense splitting application built with Java Spring Boot and JavaFX. Split bills with friends, track debts in real-time, and settle up seamlessly with built-in email notifications and multi-currency support.

![Splitty Main Menu](images/ss1.png)

## ✨ Features

### 🎯 Core Functionality

**Event Management**
- Create and join expense-sharing events with unique invite codes
- Track multiple events simultaneously with history
- Real-time synchronization across all connected clients
- Delete events from history when no longer needed

**Participant Management**
- Add participants with name, email, and optional banking details (IBAN/BIC)
- Edit participant information in real-time
- Support for international bank accounts
- Automatic participant tracking across expenses

![Event Overview](images/ss2.png)

**Expense Tracking**
- Log expenses with detailed information (payer, amount, date, category)
- Split costs evenly or among selected participants
- Multi-currency support for international events
- Filter expenses by participant or date
- Custom expense categories per event

![Add Expense](images/ss3.png)

### 📧 Communication Features

**Email Integration**
- Send event invitations directly via email (SMTP with Gmail)
- Bulk email validation with regex pattern matching
- Invalid email detection and error reporting
- Automated reminder emails for debt settlements
- All emails sent from `group4.oopp@gmail.com`

![Email Invitations](images/ss4.png)

**Debt Settlement**
- Automatic debt calculation and minimization
- Visual debt overview showing who owes whom
- One-click email reminders to debtors
- Mark debts as received when settled
- Display of complete bank account information for transfers

![Debt Overview](images/ss5.png)

### 🔐 Admin Panel

**Server Administration**
- Password-protected admin access (generated on server startup)
- View all events with participant and expense counts
- Sort events by various criteria
- Delete events from the server
- Import/export event data as JSON
- Import events from text format

![Admin Panel](images/ss6.png)

### 🌍 Internationalization

**Multi-Language Support**
- Full English and Dutch language support
- Instant language switching via UI button
- Language preference persistence
- Easy extensibility for additional languages

![Language Selection](images/ss7.png)

### ⚡ Real-Time Updates

**Live Synchronization**
- WebSocket-based real-time updates
- Long-polling fallback for compatibility
- Instant reflection of changes across all clients
- Event history updates in real-time
- Undo functionality via Recent Changes Log

**Keyboard Shortcuts**
- `Ctrl+H` - Open help menu (admin)
- `Ctrl+L` - Change language (admin)
- `Ctrl+D` - Download event data (admin)
- `Ctrl+T` - Import from text (admin)
- `Ctrl+I` - Import from file (admin)

## 🏗️ Technical Stack

**Backend:**
- Java 21
- Spring Boot
- WebSockets for real-time communication
- Long-polling for fallback support
- H2 Database for persistence
- SMTP integration (Gmail)

**Frontend:**
- JavaFX for rich desktop UI
- FXML for UI layouts
- CSS for styling
- Multi-language resource bundles

**Build & Tools:**
- Gradle for dependency management
- JUnit for testing
- Checkstyle for code quality

## 🚀 Getting Started

### Prerequisites
- Java 21 or higher
- Gradle 8.x

### Running the Application

1. **Clone the repository**
```bash
git clone https://github.com/FrozenBike265/Splitty-Expense-Tracker.git
cd Splitty-Expense-Tracker
```

2. **Start the server**
```bash
./gradlew bootRun
```
The server will start on `localhost:8080` and print the admin password in the console.

3. **Start the client** (in a new terminal)
```bash
./gradlew run
```

### Configuration

**Email Service**
Configure SMTP settings in `/server/src/main/resources/application.properties`:
- Email credentials for sending invitations and reminders
- Default configured for team email: `group4.oopp@gmail.com`

**Server URL**
Configure in `/server/src/main/resources/application.properties`:
- Default: `localhost:8080`
- Can also be changed via UI "Change Server" button

**Client Server Connection**
Configure in `/client/src/main/resources/client.properties`:
- Default: `localhost:8080`

## 🎨 Architecture Highlights

**Event Service Implementation**
- Long-polling: `/server/src/main/java/server/implementations/EventServiceImplementation.java`
- WebSocket config: `/server/src/main/java/server/WebSocketConfig.java`

**Real-Time Features**
- Instant updates across all connected clients
- Efficient change propagation with WebSockets
- Fallback to long-polling for older clients
- Change history tracking with undo capability

**Data Persistence**
- JSON export/import for event backup
- Portable event data format
- Cross-server event migration support

## 👥 Team

**OOPP Team 04 - TU Delft (2023-2024)**
- Matei Dumitrescu
- Matej Kliment
- Mario Nicolae
- Mihai Nicolae
- Teodor Mocanu
- Sebastian Mustafa

**Course:** CSE1105 - Object-Oriented Programming Project  
**Institution:** Delft University of Technology

## 📊 Project Stats

- **528 Commits** - Active development throughout the semester
- **6 Team Members** - Collaborative team project
- **96% Java** - Strong backend and desktop application focus
- **Full-Stack** - Spring Boot backend + JavaFX frontend

## 📧 Contact

For questions or feedback: [group04.oopp@gmail.com](mailto:group04.oopp@gmail.com)

---

**Note:** This project was developed as part of the CSE1105 course at TU Delft. The application demonstrates proficiency in full-stack development, real-time web technologies, and collaborative software engineering practices.
