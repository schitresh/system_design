## Microservices
- Small services that handle a specific part of the functionality and data
- They communicate with each other directly using APIs and lightweight protocols like HTTP
- Each mircoservice has its own database
  - It ensures loose coupling but may result in some duplicate data
  - Different databases can be used depending on the requirements
- Benefits
  - Each service offers a secure module boundary and can be written in different languages
  - Easy to scale independently
  - Other services continue to operate in case of failure or maintainence
- Challenges
  - Creation of large number of small services can increase complexity
  - Increased overhead of network communication, data consistency, serialization/de-serialization of data
  - Challenges to monitor, manage, test the services with each other

## Components
- API Gateway
  - Central entry point for external clients to interact with the mircoservice
  - Manges requests, handles authentication, routes requests
- Load Balancer
- Service Registry and Discovery
  - Keeps track of the locations and network addresses of all microservices
- Containerization
  - Containers like Docker encapsulate the mircoservice and its dependencies
  - Orchestration tools like Kubernetes manage the deployment, scaling, operation of containers
- Event Bus or Message Broker
  - Allows services to publish and subscribe to events
  - Enables asynchronous communication and decoupling
- Database & Caching
- Centralized Logging and Monitoring
- Fault Tolerance & Resilience Components
  - Circuit breakers, retry mechanisms, etc

## Anti-Patterns
- Data Monolith
  - Sharing a centralized database among microservices undermining independence & scalability
- Chatty Services
  - Mircoservices overly communicating for small tasks, leading to increased network overhead and latency
- Overusing Microservices
  - Creating too many microservices for trivial functionalities introducing unnecessary complexity
- Inadequate Service Boundaries
  - Poorly defined boundaries of microservice resulting in ambiguity and unclear responsibilities
- Ignoring Security
  - Neglecting security concerns in microservice risking vulnerabilities and data breaches

## Example: E-commerce
- User Service
  - Manages user accounts, authentication, preferences
  - Handles user registration, login, profile management ensuring a personalized experience for users
- Search Service
  - Indexes product information, provides relevant search results based on user queries
  - Enables users to find products quickly
- Cart Service
  - Manages the shopping cart for users (add, remove, modify items before checkout)
  - Ensures a seamless shopping experience by keeping track of selected items
- Wishlist Service
  - Manages user wishlists allowing them to save products for future purchase
  - Let's them track their desired items to purchase later or if not available currently
- Order Taking Service
  - Accepts and processes orders placed by customers
  - Validates orders, checks for product availability, initiates order fulfillment process
- Order Processing Service
  - Manages processing and fulfillment of orders
  - Coordinates with inventory, shipping, payment services to ensure timely and accurate order delivery
- Payment Service
  - Securely processes payment transactions and manages payment-related data
  - Integrates with payment gateways
- Logistics Service
  - Calculates shipping costs, assigns carriers, tracks shipments, manages delivery routes
- Warehouse Service
  - Manages inventory across warehouuses
  - Tracks inventory levels, updates stock availability, coordinates stock replenishment
- Notification Service
  - Sends notifications to users regarding their orders, promotions
  - Keeps users updated about status of their interactions with the platform
- Recommendation Service
  - Provides personalized product recommendations to users
  - Analyzes user behavior and preferences to suggest relevant products
  - Improves user experience and drives sales
