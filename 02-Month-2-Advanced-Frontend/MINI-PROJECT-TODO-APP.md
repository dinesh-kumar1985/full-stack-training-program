# Mini Project: Todo Application with React & Redux

## Project Overview
A full-featured todo application built with React and Redux, demonstrating state management, component composition, and modern React patterns.

## Features
- ✅ Add, edit, delete todos
- ✅ Mark todos as complete
- ✅ Filter todos (All, Active, Completed)
- ✅ Search functionality
- ✅ Priority levels
- ✅ Due dates
- ✅ Local storage persistence
- ✅ Responsive design

## Project Structure

```
todo-app/
├── src/
│   ├── components/
│   │   ├── TodoForm.jsx
│   │   ├── TodoList.jsx
│   │   ├── TodoItem.jsx
│   │   ├── FilterBar.jsx
│   │   └── App.jsx
│   ├── store/
│   │   ├── todoSlice.js
│   │   └── store.js
│   ├── styles/
│   │   └── App.css
│   └── main.jsx
└── package.json
```

## Setup Instructions

```bash
# Create React app
npx create-react-app todo-app
cd todo-app

# Install dependencies
npm install @reduxjs/toolkit react-redux uuid

# Start development server
npm start
```

## Implementation

### 1. Redux Slice (store/todoSlice.js)

```javascript
import { createSlice } from '@reduxjs/toolkit';
import { v4 as uuidv4 } from 'uuid';

const todoSlice = createSlice({
    name: 'todos',
    initialState: {
        items: [],
        filter: 'all', // all, active, completed
        searchTerm: ''
    },
    reducers: {
        addTodo: (state, action) => {
            state.items.push({
                id: uuidv4(),
                title: action.payload.title,
                description: action.payload.description,
                completed: false,
                priority: action.payload.priority || 'medium',
                dueDate: action.payload.dueDate || null,
                createdAt: new Date().toISOString()
            });
        },
        editTodo: (state, action) => {
            const todo = state.items.find(t => t.id === action.payload.id);
            if (todo) {
                todo.title = action.payload.title;
                todo.description = action.payload.description;
                todo.priority = action.payload.priority;
                todo.dueDate = action.payload.dueDate;
            }
        },
        toggleTodo: (state, action) => {
            const todo = state.items.find(t => t.id === action.payload);
            if (todo) {
                todo.completed = !todo.completed;
            }
        },
        deleteTodo: (state, action) => {
            state.items = state.items.filter(t => t.id !== action.payload);
        },
        setFilter: (state, action) => {
            state.filter = action.payload;
        },
        setSearchTerm: (state, action) => {
            state.searchTerm = action.payload;
        },
        loadTodos: (state, action) => {
            state.items = action.payload;
        }
    }
});

export const {
    addTodo,
    editTodo,
    toggleTodo,
    deleteTodo,
    setFilter,
    setSearchTerm,
    loadTodos
} = todoSlice.actions;

export default todoSlice.reducer;
```

### 2. Redux Store (store/store.js)

```javascript
import { configureStore } from '@reduxjs/toolkit';
import todoReducer from './todoSlice';

const store = configureStore({
    reducer: {
        todos: todoReducer
    }
});

export default store;
```

### 3. Todo Form Component (components/TodoForm.jsx)

```jsx
import React, { useState } from 'react';
import { useDispatch } from 'react-redux';
import { addTodo } from '../store/todoSlice';

function TodoForm() {
    const [title, setTitle] = useState('');
    const [description, setDescription] = useState('');
    const [priority, setPriority] = useState('medium');
    const [dueDate, setDueDate] = useState('');
    const dispatch = useDispatch();

    const handleSubmit = (e) => {
        e.preventDefault();
        
        if (title.trim()) {
            dispatch(addTodo({
                title: title.trim(),
                description: description.trim(),
                priority,
                dueDate
            }));
            
            setTitle('');
            setDescription('');
            setPriority('medium');
            setDueDate('');
        }
    };

    return (
        <form onSubmit={handleSubmit} className="todo-form">
            <div className="form-group">
                <input
                    type="text"
                    placeholder="Add a new todo..."
                    value={title}
                    onChange={(e) => setTitle(e.target.value)}
                    className="input-title"
                    required
                />
            </div>

            <div className="form-group">
                <textarea
                    placeholder="Description (optional)"
                    value={description}
                    onChange={(e) => setDescription(e.target.value)}
                    className="input-description"
                    rows="2"
                />
            </div>

            <div className="form-row">
                <div className="form-group">
                    <select
                        value={priority}
                        onChange={(e) => setPriority(e.target.value)}
                        className="input-select"
                    >
                        <option value="low">Low Priority</option>
                        <option value="medium">Medium Priority</option>
                        <option value="high">High Priority</option>
                    </select>
                </div>

                <div className="form-group">
                    <input
                        type="date"
                        value={dueDate}
                        onChange={(e) => setDueDate(e.target.value)}
                        className="input-date"
                    />
                </div>
            </div>

            <button type="submit" className="btn-add">Add Todo</button>
        </form>
    );
}

export default TodoForm;
```

### 4. Todo Item Component (components/TodoItem.jsx)

```jsx
import React, { useState } from 'react';
import { useDispatch } from 'react-redux';
import { toggleTodo, deleteTodo, editTodo } from '../store/todoSlice';

function TodoItem({ todo }) {
    const [isEditing, setIsEditing] = useState(false);
    const [editedTitle, setEditedTitle] = useState(todo.title);
    const [editedDescription, setEditedDescription] = useState(todo.description);
    const dispatch = useDispatch();

    const handleEdit = () => {
        if (editedTitle.trim()) {
            dispatch(editTodo({
                id: todo.id,
                title: editedTitle,
                description: editedDescription,
                priority: todo.priority,
                dueDate: todo.dueDate
            }));
            setIsEditing(false);
        }
    };

    const getPriorityClass = () => {
        return `priority-${todo.priority}`;
    };

    const formatDate = (date) => {
        if (!date) return '';
        return new Date(date).toLocaleDateString('en-US', {
            month: 'short',
            day: 'numeric',
            year: 'numeric'
        });
    };

    if (isEditing) {
        return (
            <li className="todo-item editing">
                <input
                    type="text"
                    value={editedTitle}
                    onChange={(e) => setEditedTitle(e.target.value)}
                    className="edit-input"
                />
                <textarea
                    value={editedDescription}
                    onChange={(e) => setEditedDescription(e.target.value)}
                    className="edit-textarea"
                />
                <div className="edit-buttons">
                    <button onClick={handleEdit} className="btn-save">Save</button>
                    <button onClick={() => setIsEditing(false)} className="btn-cancel">Cancel</button>
                </div>
            </li>
        );
    }

    return (
        <li className={`todo-item ${todo.completed ? 'completed' : ''} ${getPriorityClass()}`}>
            <div className="todo-checkbox">
                <input
                    type="checkbox"
                    checked={todo.completed}
                    onChange={() => dispatch(toggleTodo(todo.id))}
                />
            </div>

            <div className="todo-content">
                <h3>{todo.title}</h3>
                {todo.description && <p>{todo.description}</p>}
                {todo.dueDate && (
                    <span className="due-date">Due: {formatDate(todo.dueDate)}</span>
                )}
            </div>

            <div className="todo-actions">
                <button
                    onClick={() => setIsEditing(true)}
                    className="btn-edit"
                >
                    Edit
                </button>
                <button
                    onClick={() => dispatch(deleteTodo(todo.id))}
                    className="btn-delete"
                >
                    Delete
                </button>
            </div>
        </li>
    );
}

export default TodoItem;
```

### 5. Todo List Component (components/TodoList.jsx)

```jsx
import React from 'react';
import { useSelector } from 'react-redux';
import TodoItem from './TodoItem';

function TodoList() {
    const todos = useSelector(state => state.todos.items);
    const filter = useSelector(state => state.todos.filter);
    const searchTerm = useSelector(state => state.todos.searchTerm);

    let filteredTodos = todos;

    // Apply filter
    if (filter === 'active') {
        filteredTodos = filteredTodos.filter(t => !t.completed);
    } else if (filter === 'completed') {
        filteredTodos = filteredTodos.filter(t => t.completed);
    }

    // Apply search
    if (searchTerm) {
        filteredTodos = filteredTodos.filter(t =>
            t.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
            t.description.toLowerCase().includes(searchTerm.toLowerCase())
        );
    }

    // Sort by priority
    const priorityOrder = { high: 0, medium: 1, low: 2 };
    filteredTodos.sort((a, b) => priorityOrder[a.priority] - priorityOrder[b.priority]);

    return (
        <div className="todo-list-container">
            {filteredTodos.length === 0 ? (
                <p className="empty-state">
                    {todos.length === 0 ? 'No todos yet. Add one!' : 'No todos match your filter.'}
                </p>
            ) : (
                <ul className="todo-list">
                    {filteredTodos.map(todo => (
                        <TodoItem key={todo.id} todo={todo} />
                    ))}
                </ul>
            )}
        </div>
    );
}

export default TodoList;
```

### 6. Filter Bar Component (components/FilterBar.jsx)

```jsx
import React from 'react';
import { useDispatch, useSelector } from 'react-redux';
import { setFilter, setSearchTerm } from '../store/todoSlice';

function FilterBar() {
    const dispatch = useDispatch();
    const filter = useSelector(state => state.todos.filter);
    const searchTerm = useSelector(state => state.todos.searchTerm);
    const todos = useSelector(state => state.todos.items);

    const activeCount = todos.filter(t => !t.completed).length;
    const completedCount = todos.filter(t => t.completed).length;

    return (
        <div className="filter-bar">
            <div className="search-box">
                <input
                    type="text"
                    placeholder="Search todos..."
                    value={searchTerm}
                    onChange={(e) => dispatch(setSearchTerm(e.target.value))}
                    className="search-input"
                />
            </div>

            <div className="filter-buttons">
                <button
                    onClick={() => dispatch(setFilter('all'))}
                    className={`btn-filter ${filter === 'all' ? 'active' : ''}`}
                >
                    All ({todos.length})
                </button>
                <button
                    onClick={() => dispatch(setFilter('active'))}
                    className={`btn-filter ${filter === 'active' ? 'active' : ''}`}
                >
                    Active ({activeCount})
                </button>
                <button
                    onClick={() => dispatch(setFilter('completed'))}
                    className={`btn-filter ${filter === 'completed' ? 'active' : ''}`}
                >
                    Completed ({completedCount})
                </button>
            </div>
        </div>
    );
}

export default FilterBar;
```

### 7. Main App Component (components/App.jsx)

```jsx
import React, { useEffect } from 'react';
import { useDispatch } from 'react-redux';
import { loadTodos } from '../store/todoSlice';
import TodoForm from './TodoForm';
import FilterBar from './FilterBar';
import TodoList from './TodoList';
import '../styles/App.css';

function App() {
    const dispatch = useDispatch();

    // Load todos from localStorage on mount
    useEffect(() => {
        const savedTodos = localStorage.getItem('todos');
        if (savedTodos) {
            dispatch(loadTodos(JSON.parse(savedTodos)));
        }
    }, [dispatch]);

    // Save todos to localStorage whenever they change
    const saveTodos = (todos) => {
        localStorage.setItem('todos', JSON.stringify(todos));
    };

    return (
        <div className="app">
            <header className="app-header">
                <h1>📝 My Todos</h1>
                <p>Stay organized and productive</p>
            </header>

            <main className="app-main">
                <div className="container">
                    <TodoForm />
                    <FilterBar />
                    <TodoList />
                </div>
            </main>

            <footer className="app-footer">
                <p>&copy; 2026 Todo App. Built with React & Redux</p>
            </footer>
        </div>
    );
}

export default App;
```

### 8. Styling (styles/App.css)

```css
:root {
    --primary-color: #3498db;
    --success-color: #2ecc71;
    --danger-color: #e74c3c;
    --warning-color: #f39c12;
    --dark-color: #2c3e50;
    --light-color: #ecf0f1;
    --border-radius: 8px;
    --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    --transition: all 0.3s ease;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    padding: 20px;
}

.app {
    max-width: 900px;
    margin: 0 auto;
    background: white;
    border-radius: 16px;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.app-header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 40px 20px;
    text-align: center;
}

.app-header h1 {
    font-size: 2.5rem;
    margin-bottom: 10px;
}

.app-header p {
    font-size: 1rem;
    opacity: 0.9;
}

.app-main {
    flex: 1;
    padding: 30px 20px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
}

/* Todo Form */
.todo-form {
    background: var(--light-color);
    padding: 25px;
    border-radius: var(--border-radius);
    margin-bottom: 30px;
    box-shadow: var(--shadow);
}

.form-group {
    margin-bottom: 15px;
}

.form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.input-title,
.input-description,
.input-select,
.input-date,
.search-input {
    width: 100%;
    padding: 12px;
    border: 2px solid #ddd;
    border-radius: var(--border-radius);
    font-family: inherit;
    font-size: 1rem;
    transition: var(--transition);
}

.input-title:focus,
.input-description:focus,
.input-select:focus,
.input-date:focus,
.search-input:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 8px rgba(52, 152, 219, 0.2);
}

.btn-add {
    background: var(--primary-color);
    color: white;
    border: none;
    padding: 12px 30px;
    border-radius: var(--border-radius);
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    width: 100%;
}

.btn-add:hover {
    background: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
}

/* Filter Bar */
.filter-bar {
    display: flex;
    gap: 15px;
    margin-bottom: 30px;
    flex-wrap: wrap;
}

.search-box {
    flex: 1;
    min-width: 200px;
}

.filter-buttons {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
}

.btn-filter {
    background: white;
    border: 2px solid #ddd;
    padding: 8px 16px;
    border-radius: var(--border-radius);
    cursor: pointer;
    transition: var(--transition);
    font-weight: 600;
}

.btn-filter:hover {
    border-color: var(--primary-color);
    color: var(--primary-color);
}

.btn-filter.active {
    background: var(--primary-color);
    color: white;
    border-color: var(--primary-color);
}

/* Todo List */
.todo-list-container {
    background: white;
}

.empty-state {
    text-align: center;
    color: #7f8c8d;
    padding: 40px 20px;
    font-size: 1.1rem;
}

.todo-list {
    list-style: none;
}

.todo-item {
    display: flex;
    align-items: center;
    gap: 15px;
    padding: 15px;
    background: white;
    border: 1px solid #ecf0f1;
    border-radius: var(--border-radius);
    margin-bottom: 10px;
    transition: var(--transition);
    border-left: 4px solid #bdc3c7;
}

.todo-item:hover {
    box-shadow: var(--shadow);
}

.todo-item.completed {
    background: #f8f9fa;
    opacity: 0.7;
}

.todo-item.completed .todo-content h3 {
    text-decoration: line-through;
    color: #7f8c8d;
}

.todo-item.priority-high {
    border-left-color: var(--danger-color);
}

.todo-item.priority-medium {
    border-left-color: var(--warning-color);
}

.todo-item.priority-low {
    border-left-color: var(--success-color);
}

.todo-checkbox input {
    width: 24px;
    height: 24px;
    cursor: pointer;
    accent-color: var(--primary-color);
}

.todo-content {
    flex: 1;
}

.todo-content h3 {
    margin: 0 0 5px 0;
    color: var(--dark-color);
}

.todo-content p {
    color: #7f8c8d;
    font-size: 0.9rem;
    margin: 5px 0;
}

.due-date {
    display: inline-block;
    background: #ecf0f1;
    padding: 4px 8px;
    border-radius: 4px;
    font-size: 0.8rem;
    color: #555;
    margin-top: 5px;
}

.todo-actions {
    display: flex;
    gap: 8px;
}

.btn-edit,
.btn-delete,
.btn-save,
.btn-cancel {
    padding: 6px 12px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 0.85rem;
    font-weight: 600;
    transition: var(--transition);
}

.btn-edit {
    background: var(--primary-color);
    color: white;
}

.btn-edit:hover {
    background: #2980b9;
}

.btn-delete {
    background: var(--danger-color);
    color: white;
}

.btn-delete:hover {
    background: #c0392b;
}

.btn-save {
    background: var(--success-color);
    color: white;
}

.btn-save:hover {
    background: #27ae60;
}

.btn-cancel {
    background: #95a5a6;
    color: white;
}

.btn-cancel:hover {
    background: #7f8c8d;
}

/* Edit Mode */
.todo-item.editing {
    flex-direction: column;
    align-items: flex-start;
}

.edit-input,
.edit-textarea {
    width: 100%;
    padding: 10px;
    border: 2px solid var(--primary-color);
    border-radius: var(--border-radius);
    font-family: inherit;
    margin-bottom: 10px;
}

.edit-buttons {
    display: flex;
    gap: 10px;
}

/* Footer */
.app-footer {
    background: #f5f5f5;
    padding: 20px;
    text-align: center;
    color: #7f8c8d;
    border-top: 1px solid #ecf0f1;
}

/* Responsive */
@media (max-width: 768px) {
    .app-header h1 {
        font-size: 2rem;
    }

    .form-row {
        grid-template-columns: 1fr;
    }

    .filter-bar {
        flex-direction: column;
    }

    .search-box {
        width: 100%;
    }

    .filter-buttons {
        width: 100%;
    }

    .todo-item {
        flex-wrap: wrap;
    }

    .todo-actions {
        width: 100%;
    }
}
```

## Key Features Implemented

1. **State Management**: Redux Toolkit for centralized state
2. **Local Storage**: Persist todos across sessions
3. **Filtering**: Filter by status (all, active, completed)
4. **Search**: Search by title and description
5. **Priorities**: High, medium, low priority levels
6. **Due Dates**: Track todo deadlines
7. **Edit/Update**: Inline editing of todos
8. **Delete**: Remove completed todos
9. **Responsive**: Mobile-friendly design
10. **Professional UI**: Modern styling with transitions

## Learning Outcomes

✅ Redux state management
✅ Component composition
✅ React Hooks usage
✅ Form handling
✅ Local storage integration
✅ Responsive design
✅ CSS Grid and Flexbox
✅ Event handling
✅ Data filtering and searching

---

**Deployment Instructions**: Deploy to GitHub Pages, Netlify, or Vercel for live demo.
