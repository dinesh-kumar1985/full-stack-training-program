# Month 2: Advanced Frontend (React.js & JavaScript ES6+)
## Advanced JavaScript, React Fundamentals, State Management, and API Integration

**Duration:** 4 Weeks (26 Days)
**Daily Time Commitment:** 6-8 hours
**Expected Outcome:** Build production-ready React applications

---

## 🎯 Month 2 Learning Objectives

✅ Master advanced JavaScript (ES6+, OOP, Functional Programming)
✅ Learn React fundamentals and component architecture
✅ Implement state management with Hooks and Redux
✅ Master React Router for navigation
✅ Build complex forms with validation
✅ Optimize performance and rendering
✅ Integrate APIs with React
✅ Build 6+ projects with professional standards
✅ Deploy React applications

---

## 📚 Week 1: Advanced JavaScript & ES6+

### Days 1-3: ES6+ Features Deep Dive

**Topics Covered:**
- Arrow functions vs regular functions
- Destructuring (arrays and objects)
- Spread and rest operators
- Template literals
- Classes and prototypes
- Promises and error handling
- Modules (import/export)
- Async/Await patterns
- Generators and iterators

**Practical Examples:**

```javascript
// 1. Arrow Functions
const add = (a, b) => a + b;
const greet = name => `Hello, ${name}`;
const getUser = async () => {
    const response = await fetch('/api/user');
    return response.json();
};

// Arrow functions don't have their own 'this'
const person = {
    name: 'John',
    hobbies: ['reading', 'coding'],
    showHobbies() {
        this.hobbies.forEach(hobby => {
            console.log(`${this.name} likes ${hobby}`);
        });
    }
};

// 2. Destructuring
const user = { id: 1, name: 'John', email: 'john@example.com' };
const { id, name, email } = user;
const { id: userId, name: userName } = user;  // Rename

const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first, second, rest); // 1, 2, [3, 4, 5]

// 3. Spread Operator
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 }; // { a: 1, b: 2, c: 3 }

// In function calls
const numbers = [1, 2, 3];
Math.max(...numbers); // 3

// 4. Classes
class User {
    constructor(name, email) {
        this.name = name;
        this.email = email;
    }

    getInfo() {
        return `${this.name} (${this.email})`;
    }

    static createAdmin() {
        return new User('Admin', 'admin@example.com');
    }
}

class Admin extends User {
    constructor(name, email, permissions) {
        super(name, email);
        this.permissions = permissions;
    }
}

const user = new User('John', 'john@example.com');
const admin = Admin.createAdmin();

// 5. Promises
const myPromise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve('Success!');
    }, 1000);
});

myPromise
    .then(result => console.log(result))
    .catch(error => console.error(error))
    .finally(() => console.log('Done'));

// Promise.all, Promise.race, Promise.allSettled
Promise.all([promise1, promise2]).then(results => {
    // All promises resolved
});

// 6. Async/Await
async function fetchUserData(id) {
    try {
        const response = await fetch(`/api/users/${id}`);
        if (!response.ok) throw new Error('User not found');
        
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error:', error);
        return null;
    }
}

// Async operations in parallel
async function fetchMultiple() {
    const [users, posts] = await Promise.all([
        fetch('/api/users').then(r => r.json()),
        fetch('/api/posts').then(r => r.json())
    ]);
    return { users, posts };
}

// 7. Modules
// Export
export const add = (a, b) => a + b;
export default User;

// Import
import User, { add } from './math.js';
import * as Utils from './utils.js';

// 8. Template Literals
const name = 'John';
const age = 25;
const greeting = `Hello, ${name}! You are ${age} years old.`;

// Multi-line strings
const html = `
    <div class="card">
        <h2>${name}</h2>
        <p>Age: ${age}</p>
    </div>
`;

// Tagged templates
function myTag(strings, ...values) {
    return strings.join('|').concat(values.join('|'));
}

// 9. Optional Chaining & Nullish Coalescing
const user = { profile: { name: 'John' } };
const name = user?.profile?.name; // John
const age = user?.profile?.age; // undefined

const value = null ?? 'default'; // 'default'
const count = 0 ?? 'default'; // 0
```

**Practice Exercise: ES6+ Utility Library**
```javascript
// Create utility functions using ES6+ features

// Array utilities
const arrayUtils = {
    flatten: (arr) => arr.flat(Infinity),
    unique: (arr) => [...new Set(arr)],
    chunk: (arr, size) => {
        return Array.from({ length: Math.ceil(arr.length / size) }, 
            (_, i) => arr.slice(i * size, i * size + size)
        );
    },
    compact: (arr) => arr.filter(Boolean)
};

// Object utilities
const objectUtils = {
    pick: (obj, keys) => {
        return keys.reduce((acc, key) => {
            if (key in obj) acc[key] = obj[key];
            return acc;
        }, {});
    },
    omit: (obj, keys) => {
        return Object.keys(obj).reduce((acc, key) => {
            if (!keys.includes(key)) acc[key] = obj[key];
            return acc;
        }, {});
    },
    merge: (...objs) => Object.assign({}, ...objs)
};

// Function utilities
const functionUtils = {
    debounce: (func, delay) => {
        let timeoutId;
        return (...args) => {
            clearTimeout(timeoutId);
            timeoutId = setTimeout(() => func(...args), delay);
        };
    },
    throttle: (func, limit) => {
        let inThrottle;
        return (...args) => {
            if (!inThrottle) {
                func(...args);
                inThrottle = true;
                setTimeout(() => inThrottle = false, limit);
            }
        };
    },
    once: (func) => {
        let called = false;
        return (...args) => {
            if (!called) {
                called = true;
                return func(...args);
            }
        };
    }
};
```

---

### Days 4-5: Object-Oriented Programming in JavaScript

**Topics Covered:**
- Prototypes and prototype chain
- Constructor functions
- Classes and inheritance
- Static methods and properties
- Getters and setters
- Design patterns

**Examples:**

```javascript
// Constructor Function Pattern
function Vehicle(brand, model) {
    this.brand = brand;
    this.model = model;
}

Vehicle.prototype.info = function() {
    return `${this.brand} ${this.model}`;
};

function Car(brand, model, doors) {
    Vehicle.call(this, brand, model);
    this.doors = doors;
}

Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;

Car.prototype.type = function() {
    return `Car with ${this.doors} doors`;
};

// Class Pattern (Modern)
class Vehicle {
    constructor(brand, model) {
        this.brand = brand;
        this.model = model;
    }

    info() {
        return `${this.brand} ${this.model}`;
    }

    static compare(v1, v2) {
        return v1.brand === v2.brand;
    }
}

class Car extends Vehicle {
    constructor(brand, model, doors) {
        super(brand, model);
        this.doors = doors;
    }

    type() {
        return `Car with ${this.doors} doors`;
    }

    get fullInfo() {
        return `${this.info()} - ${this.type()}`;
    }

    set model(newModel) {
        if (newModel.length > 0) {
            this._model = newModel;
        }
    }

    get model() {
        return this._model || this._originalModel;
    }
}

// Singleton Pattern
class Singleton {
    static instance = null;

    constructor() {
        if (Singleton.instance) {
            return Singleton.instance;
        }
        Singleton.instance = this;
    }
}

// Observer Pattern
class EventEmitter {
    constructor() {
        this.events = {};
    }

    on(event, listener) {
        if (!this.events[event]) {
            this.events[event] = [];
        }
        this.events[event].push(listener);
    }

    emit(event, data) {
        if (this.events[event]) {
            this.events[event].forEach(listener => listener(data));
        }
    }

    off(event, listener) {
        if (this.events[event]) {
            this.events[event] = this.events[event].filter(l => l !== listener);
        }
    }
}

// Usage
const emitter = new EventEmitter();
emitter.on('userLogin', (user) => {
    console.log(`${user} logged in`);
});
emitter.emit('userLogin', 'John');
```

---

### Days 6-7: Functional Programming

**Topics Covered:**
- Pure functions
- Higher-order functions
- Function composition
- Immutability
- Functional array methods
- Currying and partial application

**Examples:**

```javascript
// Pure Functions
const add = (a, b) => a + b;  // Pure

let count = 0;
const increment = () => ++count;  // Impure - modifies external state

// Higher-Order Functions
const withLogger = (fn) => {
    return (...args) => {
        console.log(`Calling ${fn.name} with`, args);
        return fn(...args);
    };
};

const addWithLogger = withLogger(add);
addWithLogger(2, 3);

// Function Composition
const compose = (...fns) => (x) => fns.reduceRight((v, f) => f(v), x);
const pipe = (...fns) => (x) => fns.reduce((v, f) => f(v), x);

const double = (x) => x * 2;
const square = (x) => x * x;
const addOne = (x) => x + 1;

const composed = compose(square, double, addOne);
composed(5); // ((5 + 1) * 2) ^ 2 = 144

const piped = pipe(addOne, double, square);
piped(5); // ((5 + 1) * 2) ^ 2 = 144

// Immutability
const user = { name: 'John', age: 25 };
const updatedUser = { ...user, age: 26 };  // Immutable update

const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];  // Immutable concat

// Currying
const curriedAdd = (a) => (b) => a + b;
const add5 = curriedAdd(5);
add5(3); // 8

// Partial Application
const greet = (greeting, name) => `${greeting}, ${name}!`;
const sayHello = (name) => greet('Hello', name);
sayHello('John'); // 'Hello, John!'

// Functional Array Methods
const data = [
    { id: 1, name: 'John', age: 25, active: true },
    { id: 2, name: 'Jane', age: 30, active: false },
    { id: 3, name: 'Bob', age: 25, active: true }
];

// Map - transform
const names = data.map(user => user.name);

// Filter - select
const activeUsers = data.filter(user => user.active);

// Reduce - aggregate
const totalAge = data.reduce((sum, user) => sum + user.age, 0);

// Chain operations
const result = data
    .filter(user => user.age > 25)
    .map(user => ({ ...user, age: user.age + 1 }))
    .reduce((oldest, user) => user.age > oldest.age ? user : oldest);
```

---

## 📚 Week 2: React Fundamentals

### Days 8-10: React Basics & Components

**Topics Covered:**
- React setup and tooling
- JSX and rendering
- Functional components
- Props and prop drilling
- Component composition
- Conditional rendering
- Lists and keys
- Fragments

**Setup with Create React App:**

```bash
# Create React app
npx create-react-app my-react-app
cd my-react-app
npm start

# Or with Vite (faster)
npm create vite@latest my-app -- --template react
cd my-app
npm install
npm run dev
```

**Functional Components Example:**

```jsx
// Basic Component
function Welcome() {
    return <h1>Hello, React!</h1>;
}

// Component with Props
function Greeting({ name, age }) {
    return (
        <div>
            <h1>Hello, {name}!</h1>
            <p>You are {age} years old</p>
        </div>
    );
}

// Component with Children
function Card({ title, children }) {
    return (
        <div className="card">
            <h2>{title}</h2>
            <div className="card-body">
                {children}
            </div>
        </div>
    );
}

// Conditional Rendering
function UserStatus({ isLoggedIn, user }) {
    if (!isLoggedIn) {
        return <button>Login</button>;
    }

    return (
        <div>
            <p>Welcome, {user.name}</p>
            <button>Logout</button>
        </div>
    );
}

// Conditional Rendering with Ternary
function Badge({ isNew }) {
    return (
        <div>
            {isNew ? <span className="badge">NEW</span> : null}
        </div>
    );
}

// List Rendering
function UserList({ users }) {
    return (
        <ul>
            {users.map(user => (
                <li key={user.id}>
                    <h3>{user.name}</h3>
                    <p>{user.email}</p>
                </li>
            ))}
        </ul>
    );
}

// Using Fragments
function ComponentWithMultipleElements() {
    return (
        <>
            <h1>Title</h1>
            <p>Content</p>
            <footer>Footer</footer>
        </>
    );
}

// Export and Import
export default Greeting;
// Usage: import Greeting from './Greeting';
```

---

### Days 11-12: Hooks - useState and useEffect

**Topics Covered:**
- useState hook
- useEffect hook
- useContext hook
- useReducer hook
- Custom hooks
- Hook rules

**Hooks Examples:**

```jsx
import { useState, useEffect, useContext, useReducer } from 'react';

// 1. useState - State Management
function Counter() {
    const [count, setCount] = useState(0);
    const [name, setName] = useState('');

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
            <button onClick={() => setCount(count - 1)}>Decrement</button>

            <input 
                value={name} 
                onChange={(e) => setName(e.target.value)}
                placeholder="Enter name"
            />
        </div>
    );
}

// 2. useState with Objects
function UserForm() {
    const [user, setUser] = useState({ name: '', email: '' });

    const handleChange = (e) => {
        const { name, value } = e.target;
        setUser(prev => ({
            ...prev,
            [name]: value
        }));
    };

    return (
        <form>
            <input 
                name="name"
                value={user.name}
                onChange={handleChange}
                placeholder="Name"
            />
            <input 
                name="email"
                value={user.email}
                onChange={handleChange}
                placeholder="Email"
            />
        </form>
    );
}

// 3. useEffect - Side Effects
function DataFetcher() {
    const [data, setData] = useState(null);
    const [loading, setLoading] = useState(true);
    const [error, setError] = useState(null);

    useEffect(() => {
        let mounted = true;

        const fetchData = async () => {
            try {
                setLoading(true);
                const response = await fetch('/api/data');
                const result = await response.json();
                
                if (mounted) {
                    setData(result);
                    setError(null);
                }
            } catch (err) {
                if (mounted) {
                    setError(err.message);
                }
            } finally {
                if (mounted) {
                    setLoading(false);
                }
            }
        };

        fetchData();

        // Cleanup function
        return () => {
            mounted = false;
        };
    }, []); // Empty dependency array - runs once on mount

    if (loading) return <p>Loading...</p>;
    if (error) return <p>Error: {error}</p>;
    return <div>{JSON.stringify(data)}</div>;
}

// 4. useEffect with Dependencies
function SearchResults({ query }) {
    const [results, setResults] = useState([]);

    useEffect(() => {
        if (query.length > 2) {
            fetch(`/api/search?q=${query}`)
                .then(r => r.json())
                .then(data => setResults(data));
        }
    }, [query]); // Re-run when query changes

    return (
        <ul>
            {results.map(result => (
                <li key={result.id}>{result.title}</li>
            ))}
        </ul>
    );
}

// 5. Custom Hook
function useLocalStorage(key, initialValue) {
    const [storedValue, setStoredValue] = useState(() => {
        try {
            const item = window.localStorage.getItem(key);
            return item ? JSON.parse(item) : initialValue;
        } catch (error) {
            console.error(error);
            return initialValue;
        }
    });

    const setValue = (value) => {
        try {
            const valueToStore = value instanceof Function ? value(storedValue) : value;
            setStoredValue(valueToStore);
            window.localStorage.setItem(key, JSON.stringify(valueToStore));
        } catch (error) {
            console.error(error);
        }
    };

    return [storedValue, setValue];
}

// Usage of custom hook
function PersistentCounter() {
    const [count, setCount] = useLocalStorage('count', 0);

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
    );
}

// 6. useReducer - Complex State Logic
function reducer(state, action) {
    switch (action.type) {
        case 'INCREMENT':
            return { count: state.count + 1 };
        case 'DECREMENT':
            return { count: state.count - 1 };
        case 'RESET':
            return { count: 0 };
        default:
            return state;
    }
}

function AdvancedCounter() {
    const [state, dispatch] = useReducer(reducer, { count: 0 });

    return (
        <div>
            <p>Count: {state.count}</p>
            <button onClick={() => dispatch({ type: 'INCREMENT' })}>+</button>
            <button onClick={() => dispatch({ type: 'DECREMENT' })}>-</button>
            <button onClick={() => dispatch({ type: 'RESET' })}>Reset</button>
        </div>
    );
}
```

---

### Days 13-14: Props Drilling & Context API

**Topics Covered:**
- Props drilling problem
- Context API
- useContext hook
- Theme context example
- User authentication context

**Context Example:**

```jsx
import { createContext, useContext, useState } from 'react';

// Create Theme Context
const ThemeContext = createContext();

function ThemeProvider({ children }) {
    const [theme, setTheme] = useState('light');

    const toggleTheme = () => {
        setTheme(prev => prev === 'light' ? 'dark' : 'light');
    };

    const value = { theme, toggleTheme };

    return (
        <ThemeContext.Provider value={value}>
            {children}
        </ThemeContext.Provider>
    );
}

// Custom hook to use context
function useTheme() {
    const context = useContext(ThemeContext);
    if (!context) {
        throw new Error('useTheme must be used within ThemeProvider');
    }
    return context;
}

// Component using context
function Header() {
    const { theme, toggleTheme } = useTheme();

    return (
        <header className={`header ${theme}`}>
            <h1>My App</h1>
            <button onClick={toggleTheme}>
                Switch to {theme === 'light' ? 'dark' : 'light'} mode
            </button>
        </header>
    );
}

// Auth Context Example
const AuthContext = createContext();

function AuthProvider({ children }) {
    const [user, setUser] = useState(null);
    const [loading, setLoading] = useState(true);

    const login = async (email, password) => {
        setLoading(true);
        try {
            const response = await fetch('/api/login', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ email, password })
            });
            const userData = await response.json();
            setUser(userData);
            return userData;
        } finally {
            setLoading(false);
        }
    };

    const logout = () => {
        setUser(null);
    };

    return (
        <AuthContext.Provider value={{ user, loading, login, logout }}>
            {children}
        </AuthContext.Provider>
    );
}

function useAuth() {
    return useContext(AuthContext);
}

// Protected Route Component
function ProtectedRoute({ children }) {
    const { user, loading } = useAuth();

    if (loading) return <p>Loading...</p>;
    if (!user) return <p>Please login</p>;
    return children;
}

// App structure
function App() {
    return (
        <ThemeProvider>
            <AuthProvider>
                <Header />
                <ProtectedRoute>
                    <Dashboard />
                </ProtectedRoute>
            </AuthProvider>
        </ThemeProvider>
    );
}
```

---

## 📚 Week 3: State Management & Routing

### Days 15-17: Redux Toolkit

**Installation:**
```bash
npm install @reduxjs/toolkit react-redux
```

**Redux Toolkit Example:**

```javascript
// store/slices/counterSlice.js
import { createSlice } from '@reduxjs/toolkit';

const counterSlice = createSlice({
    name: 'counter',
    initialState: {
        value: 0
    },
    reducers: {
        increment: (state) => {
            state.value += 1;
        },
        decrement: (state) => {
            state.value -= 1;
        },
        incrementByAmount: (state, action) => {
            state.value += action.payload;
        }
    }
});

export const { increment, decrement, incrementByAmount } = counterSlice.actions;
export default counterSlice.reducer;

// store/store.js
import { configureStore } from '@reduxjs/toolkit';
import counterReducer from './slices/counterSlice';

const store = configureStore({
    reducer: {
        counter: counterReducer
    }
});

export default store;

// Component using Redux
import { useDispatch, useSelector } from 'react-redux';
import { increment, decrement, incrementByAmount } from './store/slices/counterSlice';

function Counter() {
    const dispatch = useDispatch();
    const count = useSelector(state => state.counter.value);

    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => dispatch(increment())}>+1</button>
            <button onClick={() => dispatch(decrement())}>-1</button>
            <button onClick={() => dispatch(incrementByAmount(5))}>+5</button>
        </div>
    );
}

// App with Redux Provider
import { Provider } from 'react-redux';

function App() {
    return (
        <Provider store={store}>
            <Counter />
        </Provider>
    );
}
```

---

### Days 18-19: React Router

**Installation:**
```bash
npm install react-router-dom
```

**Routing Example:**

```jsx
import { BrowserRouter as Router, Routes, Route, Link, useNavigate, useParams } from 'react-router-dom';

// Pages
function Home() {
    return <h1>Home Page</h1>;
}

function About() {
    return <h1>About Page</h1>;
}

function UserProfile() {
    const { userId } = useParams();
    return <h1>User Profile: {userId}</h1>;
}

function NotFound() {
    return <h1>404 - Page Not Found</h1>;
}

// Navigation Component
function Navigation() {
    return (
        <nav>
            <Link to="/">Home</Link>
            <Link to="/about">About</Link>
            <Link to="/users/123">User Profile</Link>
        </nav>
    );
}

// App Router
function App() {
    return (
        <Router>
            <Navigation />
            <Routes>
                <Route path="/" element={<Home />} />
                <Route path="/about" element={<About />} />
                <Route path="/users/:userId" element={<UserProfile />} />
                <Route path="*" element={<NotFound />} />
            </Routes>
        </Router>
    );
}
```

---

### Days 20-21: Form Handling & Validation

**Form Validation Example:**

```jsx
import { useState } from 'react';

function SignUpForm() {
    const [formData, setFormData] = useState({
        name: '',
        email: '',
        password: '',
        confirmPassword: ''
    });

    const [errors, setErrors] = useState({});
    const [submitted, setSubmitted] = useState(false);

    const validateForm = () => {
        const newErrors = {};

        if (!formData.name.trim()) {
            newErrors.name = 'Name is required';
        }

        if (!formData.email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) {
            newErrors.email = 'Invalid email format';
        }

        if (formData.password.length < 8) {
            newErrors.password = 'Password must be at least 8 characters';
        }

        if (formData.password !== formData.confirmPassword) {
            newErrors.confirmPassword = 'Passwords do not match';
        }

        return newErrors;
    };

    const handleChange = (e) => {
        const { name, value } = e.target;
        setFormData(prev => ({
            ...prev,
            [name]: value
        }));
    };

    const handleSubmit = async (e) => {
        e.preventDefault();
        const newErrors = validateForm();

        if (Object.keys(newErrors).length === 0) {
            try {
                const response = await fetch('/api/signup', {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(formData)
                });
                
                if (response.ok) {
                    setSubmitted(true);
                    setFormData({ name: '', email: '', password: '', confirmPassword: '' });
                    setErrors({});
                }
            } catch (error) {
                console.error('Error:', error);
            }
        } else {
            setErrors(newErrors);
        }
    };

    if (submitted) {
        return <p className="success">Account created successfully!</p>;
    }

    return (
        <form onSubmit={handleSubmit} noValidate>
            <div className="form-group">
                <label>Name</label>
                <input
                    type="text"
                    name="name"
                    value={formData.name}
                    onChange={handleChange}
                    className={errors.name ? 'error' : ''}
                />
                {errors.name && <span className="error-text">{errors.name}</span>}
            </div>

            <div className="form-group">
                <label>Email</label>
                <input
                    type="email"
                    name="email"
                    value={formData.email}
                    onChange={handleChange}
                    className={errors.email ? 'error' : ''}
                />
                {errors.email && <span className="error-text">{errors.email}</span>}
            </div>

            <div className="form-group">
                <label>Password</label>
                <input
                    type="password"
                    name="password"
                    value={formData.password}
                    onChange={handleChange}
                    className={errors.password ? 'error' : ''}
                />
                {errors.password && <span className="error-text">{errors.password}</span>}
            </div>

            <div className="form-group">
                <label>Confirm Password</label>
                <input
                    type="password"
                    name="confirmPassword"
                    value={formData.confirmPassword}
                    onChange={handleChange}
                    className={errors.confirmPassword ? 'error' : ''}
                />
                {errors.confirmPassword && <span className="error-text">{errors.confirmPassword}</span>}
            </div>

            <button type="submit">Sign Up</button>
        </form>
    );
}
```

---

## 📚 Week 4: Projects & Integration

### Days 22-26: Projects

**Project 1: Todo App with Redux**
- Create, read, update, delete todos
- Redux state management
- Local storage persistence
- Filter by status
- Professional UI

**Project 2: Weather App with API**
- Search city weather
- Display current weather and forecast
- Use OpenWeatherMap API
- Responsive design
- Error handling

**Project 3: Blog Application**
- Create, read, update, delete posts
- User authentication
- Comments system
- Search and filter
- React Router navigation
- Redux for state management

**Project 4: E-Commerce Product Listing**
- Product listing page
- Filter and search
- Shopping cart
- Checkout page
- Redux for cart management
- Responsive design

---

## 📋 Assignment Examples

### Assignment 1: Advanced Todo Application

**Features:**
- Add, edit, delete todos
- Mark as complete
- Filter by status (all, active, completed)
- Search functionality
- Due dates and priorities
- Local storage persistence
- Redux state management
- Responsive design
- Professional styling

**Project Structure:**
```
todo-app/
├── src/
│   ├── components/
│   │   ├── TodoForm.jsx
│   │   ├── TodoList.jsx
│   │   ├── TodoItem.jsx
│   │   └── FilterBar.jsx
│   ├── store/
│   │   ├── todoSlice.js
│   │   └── store.js
│   ├── App.jsx
│   ├── App.css
│   └── main.jsx
└── package.json
```

### Assignment 2: Weather Dashboard

**Features:**
- Search multiple cities
- Current weather display
- 5-day forecast
- Temperature unit toggle (C/F)
- Saved favorites
- Beautiful UI with weather icons
- Error handling for invalid cities
- Responsive mobile-first design

---

## ✅ Month 2 Progress Checklist

- [ ] Advanced JavaScript mastered
- [ ] ES6+ features understood and applied
- [ ] OOP in JavaScript solid
- [ ] Functional programming concepts understood
- [ ] React fundamentals solid
- [ ] Component architecture understood
- [ ] Hooks mastered (useState, useEffect, useContext, useReducer)
- [ ] Custom hooks created
- [ ] Redux Toolkit integrated
- [ ] React Router implemented
- [ ] Form validation working
- [ ] API integration complete
- [ ] 4+ projects completed
- [ ] All projects deployed
- [ ] Code quality standards met
- [ ] Performance optimization implemented

---

**Next:** [Month 3: Backend Basics (Python, Django, REST APIs)](../03-Month-3-Backend-Basics/README.md) 🚀
