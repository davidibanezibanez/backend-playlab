# Backend PlayLab

## Overview

**Backend PlayLab** is the robust RESTful API powering the **Motion Play Lab** gaming platform. It serves as the central hub for user authentication, player profile management, and the global leaderboard system.

Built with **Spring Boot** and containerized with **Docker**, this service ensures that high scores from games like *Dino Gesture Rush* or *Simon Gestures* are securely recorded and retrieved in real-time.

## Key Features

* **Secure Authentication:** Full Role-Based Access Control (RBAC) using **Spring Security** and **JWT** (JSON Web Tokens).
* **Leaderboard Engine:** Specialized logic to handle high scores, calculating rankings per game and per player.
* **Player Profiles:** Manages user statistics, history, and personal data.
* **Docker Ready:** Fully containerized application for easy deployment and scaling.
* **Data Persistence:** Robust data modeling with JPA/Hibernate and MySQL.

## Tech Stack

* **Core Framework:** Spring Boot 3 (Java 17)
* **Database:** MySQL 8.0
* **Security:** Spring Security + Auth0 JWT
* **Build Tool:** Maven
* **Containerization:** Docker & Docker Compose
* **Utilities:** Lombok, ModelMapper

## Getting Started

You can run the application either using Docker (recommended) or manually with Maven.

### Option 1: Docker (Fastest)

Ensure you have Docker and Docker Compose installed.

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/davidibanezibanez/backend-playlab.git](https://github.com/davidibanezibanez/backend-playlab.git)
    cd backend-playlab
    ```

2.  **Start the services**
    This command spins up both the API and the MySQL database automatically.
    ```bash
    docker-compose up -d --build
    ```

3.  **Verify**
    The API will be available at `http://localhost:8080/api`.

### Option 2: Manual Setup

1.  **Configure Database**
    Create a MySQL database named `playlab_db` and update `src/main/resources/application.properties` with your credentials.

2.  **Build and Run**
    ```bash
    ./mvnw spring-boot:run
    ```

## API Endpoints Summary

| Module | Method | Endpoint | Description |

| **Auth** | `POST` | `/api/auth/login` | Authenticate user & get Token |

| **Auth** | `POST` | `/api/auth/register` | Register a new player |

| **Games** | `GET` | `/api/games` | List available games |

| **Scores** | `POST` | `/api/scores` | Submit a new high score |

| **Scores** | `GET` | `/api/scores/top/{gameId}` | Get leaderboard for a game |

| **Profile** | `GET` | `/api/profile/me` | Get current player stats |

## Database Schema

The system initializes with a standard schema including:
* `users` & `roles`: Identity management.
* `games`: Registry of supported games.
* `scores`: Relational historical data of player performance.

## Contributing

1.  Fork the repository.
2.  Create your feature branch (`git checkout -b feature/NewEndpoint`).
3.  Commit your changes (`git commit -m 'Add some NewEndpoint'`).
4.  Push to the branch (`git push origin feature/NewEndpoint`).
5.  Open a Pull Request.

## Contact

David Ibáñez - https://www.linkedin.com/in/davidibanezibanez/

Project Link: [https://github.com/davidibanezibanez/backend-playlab](https://github.com/davidibanezibanez/backend-playlab)
