Day 1 - 26 June 2025
Topics Covered:
Introduction to React.js, component-based architecture, JSX syntax, and setting up the development environment
 What I Did:
Today marked the beginning of my ecommerce website training using React.js. I started by understanding the fundamentals of React, which is a JavaScript library for building user interfaces. I learned about components, which are reusable pieces of UI that can be combined to create complex applications.
I set up my development environment by installing Node.js and creating my first React project using Vite. The project structure was quite different from traditional HTML/CSS/JavaScript projects, with everything organized in a component-based manner. I explored the src folder structure and learned about the importance of organizing code properly.
I created my first component called Home.jsx and learned about JSX syntax, which allows me to write HTML-like code directly in JavaScript. I also explored the concept of props and state management. The JSX syntax felt very intuitive as it combined the power of JavaScript with the familiarity of HTML markup.
I learned about the virtual DOM concept and how React efficiently updates the actual DOM by comparing it with a virtual representation. This optimization technique makes React applications much faster than traditional DOM manipulation.
I also explored the public folder and learned about static assets like images, icons, and other files that don't need to be processed by the build system. I placed some initial images in the public folder for my ecommerce site.
Here's an example of my first component structure:
const Home = () => {
    return (
        <div>
            <h1>Welcome to My Ecommerce Site</h1>
            <p>This is my first React component</p>
        </div>
    );
};
I also learned about the importance of component reusability and how it makes the code more maintainable and organized. The concept of breaking down complex UIs into smaller, reusable components was a game-changer for me.
I spent time understanding the package.json file and how dependencies are managed in React projects. I learned about different types of dependencies like dependencies and devDependencies, and how npm or yarn manages these packages.
The day ended with me feeling confident about the basic React concepts and excited to dive deeper into more advanced topics like state management and component lifecycle.


Day 2 - 27 June 2025 (Friday)
 Topics Covered:
React hooks (useState, useEffect), component lifecycle, and basic state management
What I Did:
Today I delved deeper into React hooks, specifically useState and useEffect. I learned how useState allows components to have local state, which is crucial for building interactive applications. The concept of state management was completely new to me, and I found it fascinating how React handles component re-rendering when state changes.
I implemented state management in my Home.jsx component to handle product data. I created multiple state variables for different product categories:
const [machines, setMachines] = useState([]);
const [acParts, setAcParts] = useState([]);
const [tvParts, setTvParts] = useState([]);
I learned about the importance of using the setter functions provided by useState to update state, as directly modifying state variables doesn't trigger re-renders. This was a crucial concept for building dynamic applications.
I also learned about useEffect hook for handling side effects like API calls. I implemented data fetching functions for different product categories:
const fetchMachines = async () => {
    try {
        const res = await axios.get("http://localhost:3000/machine");
        const machinesWithType = res.data.map(machine => ({
            ...machine,
            productType: 'machine'
        }));
        setMachines(machinesWithType);
    } catch (error) {
        console.error("Error fetching machines:", error);
    }
};
Understanding the component lifecycle and when to use different hooks was crucial for building responsive applications. I learned about the dependency array in useEffect and how it controls when the effect runs.
I also explored the concept of cleanup functions in useEffect to prevent memory leaks when components unmount. This was particularly important for handling API calls and event listeners.
The day ended with me having a solid understanding of React hooks and how they enable functional components to have state and side effects, which was previously only possible with class components.


Day 3 - 30 June 2025 (Monday)
Topics Covered:
React Router, navigation, and creating multiple pages for the ecommerce site
What I Did:
Today I learned about React Router for handling navigation between different pages in my ecommerce application. I installed react-router-dom and set up the routing structure. This was a crucial step in making my application feel like a real multi-page website rather than a single-page application.
I created multiple components for different product categories in the src folder:
Washingmachine.jsx for washing machine products
Tv.jsx for TV products
Ac.jsx for AC products
I implemented the routing in my App.jsx:
<Routes>
    <Route path="/" element={<Home />} />
    <Route path="/washingmachine" element={<Washingmachine />} />
    <Route path="/tv" element={<Tv />} />
    <Route path="/ac" element={<Ac />} />
</Routes>
I also learned about dynamic routing using parameters, which I used in my DynamicCard.jsx component to display individual product details:
const { _id, type } = useParams();
This allowed me to create a single component that could handle different product types dynamically. I was amazed by how React Router could extract URL parameters and make them available to components.
I implemented navigation links in my navbar.jsx component using Link and NavLink components from React Router. I learned about the difference between these two - Link for basic navigation and NavLink for navigation with active state styling.
I also explored nested routing and how to create layouts that persist across different routes. This was particularly useful for maintaining the navigation bar and footer across all pages.
The day ended with me having a fully functional multi-page ecommerce application with proper navigation between different product categories.


Day 4 - 1 July 2025 (Tuesday)
 Topics Covered:
Material-UI (MUI) components, styling, and creating responsive UI components
 What I Did:
Today I explored Material-UI, a popular React UI framework that provides pre-built components. I installed @mui/material and @emotion/react to enhance the visual appeal of my ecommerce site.
I learned about various MUI components like:
Card, CardContent, CardMedia for product displays
Button, TextField for forms and interactions
Box, Typography for layout and typography
IconButton for interactive elements
I implemented these components throughout my application to create a consistent and professional user interface. The Material-UI components provided a modern, clean look that significantly improved the visual appeal of my ecommerce site.
I also learned about MUI's sx prop for custom styling and responsive design principles. The sx prop was particularly powerful as it allowed me to write CSS-in-JS with theme-aware properties. I explored how to create responsive layouts that adapt to different screen sizes.
I explored MUI's theme system and how to customize colors, typography, and spacing. I created a consistent design system across all my components using MUI's theming capabilities. This helped maintain visual consistency throughout the application.
I also learned about MUI's grid system and how to create responsive layouts using the Grid component. This was crucial for making my product displays look good on both desktop and mobile devices.
The day ended with me having a much more polished and professional-looking ecommerce interface with consistent styling and responsive design. The Material-UI components made the development process much faster and the final result much more professional.


Day 5 - 2 July 2025 (Wednesday)
   Topics Covered:
Axios for API calls, HTTP methods, and connecting frontend to backend
 What I Did:
Today I learned about Axios, a popular HTTP client for making API requests from React to my backend server. I installed axios and started implementing API calls throughout my application.
I created data fetching functions for different product categories:
const fetchMachines = async () => {
    try {
        const res = await axios.get("http://localhost:3000/machine");
        const machinesWithType = res.data.map(machine => ({
            ...machine,
            productType: 'machine'
        }));
        setMachines(machinesWithType);
    } catch (error) {
        console.error("Error fetching machines:", error);
    }
};
I also implemented error handling for API calls and learned about different HTTP methods (GET, POST, PUT, DELETE). Understanding how to handle asynchronous operations and loading states was crucial for building a smooth user experience.
I learned about CORS (Cross-Origin Resource Sharing) and how to configure it properly between frontend and backend. This was a common issue when connecting React applications to backend APIs.
I explored how to handle different response formats and implement proper error boundaries. I also learned about request interceptors and response interceptors in Axios for handling common scenarios like authentication tokens.
The day ended with me having a solid understanding of how to connect my React frontend to a backend API and handle various HTTP operations effectively.


Day 6 - 3 July 2025 (Thursday)
 Topics Covered:
Form handling, controlled components, and creating product management interfaces
What I Did:
Today I focused on creating forms for product management. I built ProductForm.jsx component for adding and editing products. I learned about controlled components, where form inputs are controlled by React state.
I implemented form validation and learned about handling form submissions:
const handleSubmit = async (e) => {
    e.preventDefault();
    try {
        const formData = new FormData();
        formData.append('title', title);
        formData.append('newprice', newprice);
        // ... other form fields
        await axios.post(http://localhost:3000/${productType}, formData);
    } catch (error) {
        console.error("Error submitting form:", error);
    }
};
I also created ProductList.jsx for displaying and managing products with edit and delete functionality. Learning about form handling and validation was essential for building a complete ecommerce management system.
I explored different form validation techniques including HTML5 validation attributes and custom JavaScript validation. I also learned about handling file uploads in forms and how to use FormData for sending multipart data.
I implemented proper error handling for forms and learned about user feedback mechanisms like success messages and error notifications. This was crucial for providing a good user experience.
The day ended with me having a comprehensive understanding of form handling in React and how to create robust, user-friendly forms for data input and management.


Day 7 - 4 July 2025 (Friday)
 Topics Covered:
File upload handling, Multer middleware, and image management
 What I Did:
Today I learned about handling file uploads in my ecommerce application. I implemented image upload functionality for products using FormData and Multer middleware on the backend.
I created the upload configuration in my backend:
const storage = multer.diskStorage({
    destination: function (req, file, cb) {
        cb(null, path.resolve(./public/machine/));
    },
    filename: function (req, file, cb) {
        const fileName = ${Date.now()}-${file.originalname};
        cb(null, fileName);
    },
});
I learned about handling multiple file uploads for product images:
const uploadFields = upload.fields([
    { name: 'image', maxCount: 1 },
    { name: 'image2', maxCount: 1 },
    { name: 'image3', maxCount: 1 }
]);I explored how to handle different file types and implement file size restrictions. I also learned about serving static files from the backend and how to organize uploaded files in the public folder structure.
I implemented proper error handling for file uploads and learned about progress indicators for better user experience. This was crucial for creating a professional ecommerce site with product galleries.
The day ended with me having a solid understanding of file upload handling and how to manage images effectively in a web application.


Day 8 - 7 July 2025 (Monday)
 Topics Covered:
Context API, global state management, and shopping cart functionality
 What I Did:
Today I implemented the shopping cart functionality using React's Context API. I created CartContext.jsx to manage the global state of the shopping cart across all components.
I learned about creating context providers and consumers:
const CartContext = createContext();

export const CartProvider = ({ children }) => {
    const [cart, setCart] = useState([]);
    
    const addToCart = (product) => {
        setCart(prevCart => [...prevCart, product]);
    };
    
    return (
        <CartContext.Provider value={{ cart, addToCart }}>
            {children}
        </CartContext.Provider>
    );
};
I implemented the cart functionality in my Card.jsx component:
const { addToCart } = useCart();

const handleAddToCart = () => {
    addToCart(product);
    toast.success('Added to cart!');
};
I also created CartDrawer.jsx component to display the cart contents. Learning about global state management was essential for building a functional ecommerce application.
I explored how to persist cart data and handle cart operations like removing items and updating quantities. I also learned about the importance of providing a smooth shopping experience.
The day ended with me having a fully functional shopping cart system that could be accessed from any component in the application.


Day 9 - 8 July 2025 (Tuesday)
 Topics Covered:
User authentication, Firebase integration, and signup functionality
 What I Did:
Today I implemented user authentication features using Firebase. I created signup.jsx component for user registration and integrated Firebase authentication. I learned about handling user credentials and session management with Firebase.
I implemented the signup functionality using Firebase:
const handleSubmit = async (e) => {
    e.preventDefault();
    try {
        const res = await axios.post('http://localhost:3000/register', {
            email, uid, phone, password
        });
        // Handle successful registration
    } catch (error) {
        console.error("Registration error:", error);
    }
};
I also created authentication middleware and learned about protecting routes. Understanding user authentication was crucial for building a secure ecommerce platform.
I implemented form validation and error handling for the signup form. I also learned about Firebase's built-in security features and best practices for handling user credentials.
I explored how to manage user sessions with Firebase and implement logout functionality. I also learned about the importance of providing clear feedback to users during authentication processes.
The day ended with me having a secure authentication system using Firebase that could handle user registration and session management effectively.


Day 10 - 9 July 2025 (Wednesday)
 Topics Covered:
Order management, order creation, and order tracking
 What I Did:
Today I implemented the order management system. I created the order creation functionality in my Delivery.jsx component, where users can place orders with delivery details.
I implemented the order submission:
const handleSubmit = async (e) => {
    e.preventDefault();
    try {
        const orderData = {
            deliveryDetails: deliveryData,
            items: cartItems,
            totalAmount: totalAmount,
            userId: currentUser.id
        };
        await axios.post('http://localhost:3000/orders', orderData);
    } catch (error) {
        console.error("Order submission error:", error);
    }
};
I created the Order model in my backend and implemented order storage and retrieval. I also built Myorders.jsx component for users to view their order history.
I explored how to handle order status updates and implement order tracking functionality. I also learned about calculating order totals and handling different payment scenarios.
I implemented proper error handling for order operations and learned about order confirmation processes. This was crucial for providing a complete ecommerce experience.
The day ended with me having a comprehensive order management system that could handle the complete order lifecycle from creation to delivery.


Day 11 - 10 July 2025 (Thursday)
 Topics Covered:
Search functionality, filtering, and product discovery
 What I Did:
Today I implemented search and filtering functionality for products. I created SearchResults.jsx component and implemented search across different product categories.
I learned about implementing search with debouncing and real-time results:
const handleSearch = async (query) => {
    if (query.trim()) {
        try {
            const res = await axios.get(http://localhost:3000/api/machine-search?q=${query});
            setSearchResults(res.data);
        } catch (error) {
            console.error("Search error:", error);
        }
    }
};
I also implemented filtering by product type, price range, and other criteria. Understanding search and filtering was crucial for improving user experience and product discovery.
I created the search API endpoint in my backend to handle search queries efficiently. I also learned about implementing search suggestions and autocomplete functionality.
I explored how to optimize search performance and implement proper indexing for better search results. I also learned about handling search edge cases and providing meaningful results.
The day ended with me having a robust search and filtering system that significantly improved the user experience of my ecommerce platform.


Day 12 - 11 July 2025 (Friday)
 Topics Covered:
Individual product details, dynamic routing, and product information display
 What I Did:
Today I implemented the individual product details functionality. I created DynamicCard.jsx component to display detailed information about specific products when users click on them.
I learned about dynamic routing using React Router parameters:
const { _id, type } = useParams();  // Get product ID and type from URL

useEffect(() => {
    const fetchProductById = async () => {
        try {
            const res = await axios.get(http://localhost:3000/${productType}/${_id});
            setProduct(res.data);
        } catch (error) {
            console.error("Error fetching product:", error);
        }
    };
    if (_id) {
        fetchProductById();
    }
}, [_id]);
I implemented the backend route to fetch individual products:
app.get("/machine/:id", async (req, res) => {
    try {
        const product = await Machine.findById(req.params.id);
        if (!product) {
            return res.status(404).json({ message: "Product not found" });
        }
        res.json(product);
    } catch (error) {
        res.status(500).json({ message: "Server error", error });
    }
});
I also created the routing structure to handle different product types (machine, tv, ac) dynamically. This was crucial for creating a proper product browsing experience.
The day ended with me having a complete product detail system that allowed users to view comprehensive information about individual products before making purchase decisions.


Day 13 - 14 July 2025 (Monday)
 Topics Covered:
Review system, rating functionality, and user feedback
 What I Did:
Today I implemented the review and rating system for products. I created Review.jsx and Reviews.jsx components for users to leave reviews and ratings.
I implemented the review submission:
const handleSubmit = async (e) => {
    e.preventDefault();
    try {
        const formData = new FormData();
        formData.append('rating', rating);
        formData.append('comment', comment);
        formData.append('productId', productId);
        await axios.post('http://localhost:3000/reviews', formData);
    } catch (error) {
        console.error("Review submission error:", error);
    }
};
I created the Review model in my backend and implemented review storage and retrieval. I also built the review display functionality to show existing reviews for products.
On the backend side, I implemented the review routes in server.js
app.post('/reviews', reviewUpload.array('images', 5), async (req, res) => {
    try {
        const reviewData = {
            ...req.body,
            images: req.files ? req.files.map(file => /reviews/${file.filename}) : []
        };
        const review = new Review(reviewData);
        await review.save();
        res.status(201).json(review);
    } catch (error) {
        res.status(400).json({ message: error.message });
    }
});
I also implemented the review retrieval endpoint and learned about handling review moderation and spam prevention.
The day ended with me having a comprehensive review system that enhanced user trust and helped customers make informed purchase decisions.


Day 14 - 15 July 2025 (Tuesday)
 Topics Covered:
Admin panel, product management, and administrative functions
 What I Did:
Today I created the admin panel functionality. I built ProductTypeEditPanel.jsx for administrators to manage products across different categories.
I implemented admin authentication and authorization:
const ADMIN_PASSWORD = 'admin123';
const [isAuthenticated, setIsAuthenticated] = useState(false);

const handleAuth = (password) => {
    if (password === ADMIN_PASSWORD) {
        setIsAuthenticated(true);
    }
};
I created product management functions including add, edit, and delete operations:
const handleDelete = async (product) => {
    if (!window.confirm('Are you sure you want to delete this product?')) return;
    const backendType = type === 'washingmachine' ? 'machine' : type;
    try {
        await axios.delete(http://localhost:3000/${backendType}/${product._id});
        fetchProducts();
    } catch (error) {
        alert('Error deleting product');
    }
};
I also built Users.jsx component for user management. Learning about admin functionality was crucial for maintaining the ecommerce platform.
I implemented the backend routes for admin operations and learned about proper authorization and access control. I also explored how to handle admin-specific features like bulk operations and analytics.
The day ended with me having a comprehensive admin panel that could effectively manage all aspects of the ecommerce platform.


Day 15 - 16 July 2025 (Wednesday)
 Topics Covered:
Backend optimization, database models, and server performance improvements
 What I Did:
Today I focused on optimizing the backend performance of my ecommerce application. I worked on improving the database models, service layer, and server.js file for better performance and maintainability.
I optimized the database models in the models folder by implementing proper schema validation and indexing. I improved the Machine, Product, and Order models to handle data more efficiently:
// In models/machine.js - optimized schema
const machineSchema = new mongoose.Schema({
    title: { type: String, required: true, index: true },
    newprice: { type: Number, required: true, index: true },
    stock: { type: Number, default: 0 }
}, { timestamps: true });
I enhanced the service layer in the service folder by implementing better error handling and data validation. I created optimized service functions for handling business logic:
// In service/authentication.js - improved error handling
const validateUser = async (userData) => {
    try {
        // Enhanced validation logic
        return await User.findOne(userData);
    } catch (error) {
        throw new Error('User validation failed');
    }
};
I optimized the server.js file by implementing proper middleware ordering and request handling:
// Improved middleware configuration
app.use(express.json({ limit: '2mb' }));
app.use(express.urlencoded({ extended: true, limit: '2mb' }));
app.use(cors(corsOptions));
I also implemented proper error handling middleware and request logging for better debugging and monitoring.
The day ended with me having a highly optimized backend architecture with improved models, services, and server configuration.


Day 16 - 17 July 2025 (Thursday)
 Topics Covered:
Database models optimization and schema improvements
 What I Did:
Today I focused on optimizing the database models in the models folder. I worked on improving the schema definitions for better data integrity and performance.
I enhanced the Machine model by implementing proper validation and indexing:
// In models/machine.js - optimized schema
const machineSchema = new mongoose.Schema({
    title: { type: String, required: true, index: true },
    newprice: { type: Number, required: true, index: true },
    stock: { type: Number, default: 0 }
}, { timestamps: true });
// In models/Order.js - enhanced order structure
const orderSchema = new mongoose.Schema({
    userId: { type: String, required: true, index: true },
    deliveryDetails: { type: Object, required: true },
    items: [{ type: Object }],
    totalAmount: { type: Number, required: true },
    orderStatus: { type: String, default: 'pending' }
}, { timestamps: true });
I learned about MongoDB indexing strategies and implemented proper indexes for frequently queried fields. This significantly improved query performance.
The day ended with me having optimized database models that could handle data more efficiently and provide better performance.


Day 17 - 18 July 2025 (Friday)
 Topics Covered:
Service layer implementation and business logic optimization
 What I Did:
Today I focused on enhancing the service layer in the service folder. I worked on implementing better business logic separation and error handling for the authentication service.
I improved the authentication service by implementing more robust user validation:
// In service/authentication.js - enhanced validation
const validateUser = async (userData) => {
    try {
        const user = await User.findOne(userData);
        if (!user) {
            throw new Error('User not found');
        }
        return user;
    } catch (error) {
        throw new Error('User validation failed: ' + error.message);
    }
};
I also created service functions for handling complex business operations like order processing and inventory management. I learned about the importance of separating business logic from route handlers.
I implemented proper error handling and logging in the service layer. I also explored how to create reusable service functions that could be used across different parts of the application.
I learned about the service-oriented architecture pattern and how it helps in maintaining clean, testable code.
The day ended with me having a well-structured service layer that could handle complex business operations efficiently.


Day 18 - 21 July 2025 (Monday)
 Topics Covered:
Server.js creation and middleware setup
 What I Did:
Today I created the main server.js file and set up the basic server configuration. I learned about Express.js framework and how to create a web server using Node.js.
I created the basic server setup:
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const app = express();

app.use(express.json());
app.use(cors(corsOptions));
I implemented the MongoDB connection:
mongoose
    .connect('mongodb://localhost:27017/Ecommerce', {
        useNewUrlParser: true,
        useUnifiedTopology: true
    })
    .then((e) => console.log("MongoDB connected"))
    .catch(err => {
        console.error("MongoDB connection error:", err);
        process.exit(1);
    });
I created the basic middleware configuration and learned about handling different types of requests. I also set up the static file serving for images and other assets.
I implemented the basic route structure and learned about organizing API endpoints properly. This was crucial for building a scalable backend architecture.
The day ended with me having a functional server that could handle basic HTTP requests and connect to the database.


Day 19 - 22 July 2025 (Tuesday)
 Topics Covered:
API routes implementation and endpoint creation
 What I Did:
Today I implemented the core API routes in my server.js file. I created endpoints for handling different product categories and user operations.
I created the machine routes for product management:
app.post("/machine", uploadFields, async (req, res) => {
    try {
        const { title, newprice, oldprice, discount, delivery, description, feature, heading, stock } = req.body;
        const newMachine = new Machine({
            title,
            image: imageUrl1,
            image2: imageUrl2,
            image3: imageUrl3,
            newprice,
            oldprice,
            discount,
            delivery,
            description,
            feature,
            heading,
            stock,
        });
        await newMachine.save();
        res.status(201).json({ message: "Machine added successfully", machine: newMachine });
    } catch (error) {
        console.error("Error adding machine:", error);
        res.status(500).json({ message: "Internal server error" });
    }
});
I also implemented the GET routes for fetching products:
app.get("/machine", async (req, res) => {
    try {
        const machines = await Machine.find();
        res.status(200).json(machines);
    } catch (error) {
        console.error("Error fetching machines:", error);
        res.status(500).json({ message: "Internal server error" });
    }
});
I learned about proper error handling and HTTP status codes. I also implemented similar routes for TV and AC products.
The day ended with me having a complete set of API endpoints for product management operations.


Day 20 - 23 July 2025 (Wednesday)
 Topics Covered:
User authentication routes and order management implementation
 What I Did:
Today I implemented the user authentication and order management routes in my server.js file. I created endpoints for user registration and order processing.
I created the user registration route:
app.post("/register", async (req, res) => {
    const { email, uid, phone, password } = req.body;
    try {
        let user = await Register.findOne({ email });
        if (!user) {
            user = new Register({ email, uid, phone, password });
            await user.save();
        }
        res.status(201).json({ message: "User registered successfully", user });
    } catch (error) {
        res.status(500).json({ message: "Error saving user", error });
    }
});
I implemented the order creation and management routes:
app.post("/orders", async (req, res) => {
    try {
        const { deliveryDetails, items, totalAmount, userId } = req.body;
        const newOrder = new Order({
            userId,
            deliveryDetails,
            items,
            totalAmount
        });
        const savedOrder = await newOrder.save();
        res.status(201).json(savedOrder);
    } catch (error) {
        console.error('Error creating order:', error);
        res.status(500).json({ message: "Error creating order", error: error.message });
    }
});
I also created routes for fetching user orders and order history. I learned about handling complex data structures and implementing proper validation.
The day ended with me having a complete authentication and order management system in place.


Day 21 - 24 July 2025 (Thursday)
 Topics Covered:
File upload system implementation and delivery management
 What I Did:
Today I implemented the file upload system and delivery management in my server.js file. I created endpoints for handling file uploads and delivery operations.
I created the file upload configuration:
const storage = multer.diskStorage({
    destination: function (req, file, cb) {
        cb(null, path.resolve(./public/machine/));
    },
    filename: function (req, file, cb) {
        const fileName = ${Date.now()}-${file.originalname};
        cb(null, fileName);
    },
});

const upload = multer({ storage: storage });
const uploadFields = upload.fields([
    { name: 'image', maxCount: 1 },
    { name: 'image2', maxCount: 1 },
    { name: 'image3', maxCount: 1 }
]);
I implemented the delivery management routes:
app.post("/delivery", async (req, res) => {
    const deliverydata = new Delivery(req.body);
    await deliverydata.save();
    res.json(deliverydata);
});

app.get("/data", async (req, res) => {
    try {
        const deliveries = await Delivery.find();
        res.status(200).json(deliveries);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
});
I also created routes for handling different file types and implementing proper file validation. I learned about handling multipart form data and file storage management.
The day ended with me having a complete file upload and delivery management system integrated into the backend.


Day 22 - 25 July 2025 (Friday)
 Topics Covered:
Final testing, bug fixes, documentation, and project completion
 What I Did:
Today was the final day of my ecommerce website training, and I focused on comprehensive testing and completing all necessary components. I conducted thorough testing of all major functionalities including user registration, product browsing, shopping cart operations, order placement, review system, and admin panel functions.
I completed the final frontend components including Invoice.jsx and InvoicePage.jsx for order management:
const Invoice = ({ orderData }) => {
    return (
        <div className="invoice-container">
            <div className="invoice-header">
                <h2>Order Invoice</h2>
                <p>Order ID: {orderData._id}</p>
                <p>Date: {new Date(orderData.orderDate).toLocaleDateString()}</p>
            </div>
            <div className="invoice-items">
                {orderData.items.map((item, index) => (
                    <div key={index} className="invoice-item">
                        <span>{item.title}</span>
                        <span>₹{item.newprice}</span>
                    </div>
                ))}
            </div>
            <div className="invoice-total">
                <h3>Total: ₹{orderData.totalAmount}</h3>
            </div>
        </div>
    );
};
I fixed several critical bugs discovered during testing, including CORS issues with API calls, image upload problems, navigation issue. I also resolved issues with the shopping cart functionality and order processing.
I implemented final optimizations including code splitting, lazy loading, and performance improvements. I also added proper error boundaries and loading states throughout the application.
I conducted cross-browser testing to ensure the application works perfectly across all browsers. I also tested the application under different network conditions to ensure reliability.
I learned about the importance of thorough testing for maintaining and scaling applications. I also gained valuable insights into the complete software development lifecycle.
Key Learnings from the Training:
Component-based architecture makes code more maintainable and reusable
State management is crucial for building interactive applications
API integration requires proper error handling and loading states
User experience should be prioritized in ecommerce applications
Performance optimization is crucial for user satisfaction
Security considerations are vital for handling user data
Cross-browser compatibility ensures wider user reach
 Project Achievements:
Complete ecommerce platform with product management, user authentication, shopping cart, order processing, and admin panel
Robust backend with proper error handling and data validation
Professional UI/UX using Material-UI components
Comprehensive testing
Performance optimized application ready for production
This training has given me a solid foundation in building full-stack web applications using React.js and MongoDB. I've learned not just the technical skills, but also the importance of user experience, testing. The hands-on experience of building a complete ecommerce platform has been invaluable, and I'm excited to continue learning and building more complex applications in the future. I now have the confidence to tackle real-world projects and contribute effectively to web development teams.
The journey from basic React concepts to a fully functional ecommerce platform has been incredibly rewarding, and I'm grateful for the comprehensive learning experience that has prepared me for professional web development.



