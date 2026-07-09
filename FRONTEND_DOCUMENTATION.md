# 🎨 Frontend Documentation - Contractor Marketplace

## 📋 Table of Contents
1. [Overview](#overview)
2. [Technology Stack](#technology-stack)
3. [Project Architecture](#project-architecture)
4. [Getting Started](#getting-started)
5. [Folder Structure](#folder-structure)
6. [Core Features](#core-features)
7. [State Management](#state-management)
8. [Routing System](#routing-system)
9. [UI Components](#ui-components)
10. [API Integration](#api-integration)
11. [Authentication Flow](#authentication-flow)
12. [Development Guidelines](#development-guidelines)
13. [Build & Deployment](#build--deployment)
14. [Performance Optimization](#performance-optimization)
15. [Testing Strategy](#testing-strategy)

---

## 🎯 Overview

**Project Name**: Contractor Marketplace Frontend  
**Type**: Single Page Application (SPA)  
**Purpose**: A comprehensive platform connecting clients with contractors

### Key Features
- 🏠 **Contractor Discovery** - Search and filter contractors by specialty, location, rating
- 👤 **User Authentication** - Secure login/signup with role-based access
- 📱 **Responsive Design** - Mobile-first approach with Tailwind CSS
- 🤖 **AI Chatbot** - Intelligent assistant for user queries
- 📊 **Dashboard System** - Role-specific dashboards for different user types
- 🔍 **Advanced Search** - Powerful filtering and search capabilities
- ⭐ **Review System** - Client reviews and ratings for contractors
- 📄 **Service Catalog** - Detailed service and product listings

---

## 🛠️ Technology Stack

### Core Technologies
- **React 18.3.1** - Modern React with hooks and concurrent features
- **TypeScript 5.8.3** - Type-safe JavaScript with full IDE support
- **Vite 5.4.19** - Fast build tool with HMR and optimized bundling

### State Management
- **Redux Toolkit 2.9.2** - Modern Redux with simplified API
- **Redux Persist 6.0.0** - Persist state across browser sessions
- **React Redux 9.2.0** - React bindings for Redux

### Routing & Navigation
- **React Router DOM 6.30.1** - Declarative routing for React

### UI & Styling
- **Tailwind CSS 3.4.17** - Utility-first CSS framework
- **Radix UI** - Accessible, unstyled UI primitives
- **shadcn/ui** - Beautiful, reusable components built on Radix
- **Lucide React 0.562.0** - Beautiful & consistent icon library
- **Framer Motion 12.24.8** - Production-ready motion library

### Forms & Validation
- **React Hook Form 7.61.1** - Performant forms with easy validation
- **Zod 3.25.76** - TypeScript-first schema validation

### Data Fetching
- **TanStack Query 5.83.0** - Powerful data synchronization for React
- **Axios 1.13.2** - Promise-based HTTP client

### Additional Libraries
- **Swiper 12.0.3** - Modern touch slider
- **Recharts 2.15.4** - Composable charting library
- **Date-fns 3.6.0** - Modern JavaScript date utility library
- **Sonner 1.7.4** - Opinionated toast component

---

## 🏗️ Project Architecture

### Architecture Pattern
**Feature-Based Architecture** with clear separation of concerns:

```
Frontend (React/TypeScript)
├── Presentation Layer (Components/Pages)
├── State Management Layer (Redux)
├── Service Layer (API calls)
├── Type Layer (TypeScript definitions)
└── Utility Layer (Helper functions)
```

### Design Principles
1. **Component Composition** - Small, reusable components
2. **Type Safety** - Full TypeScript coverage
3. **Separation of Concerns** - Clear boundaries between layers
4. **Accessibility First** - WCAG compliant components
5. **Performance Optimized** - Code splitting and lazy loading
6. **Mobile First** - Responsive design from ground up

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ 
- npm or yarn package manager
- Git

### Installation
```bash
# Clone the repository
git clone <repository-url>
cd contractor-marketplace

# Install dependencies
npm install

# Start development server
npm run dev
```

### Available Scripts
```bash
npm run dev          # Start development server (http://localhost:8080)
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
npm run lint --fix   # Fix linting issues
```

### Environment Variables
Create `.env` file in root:
```env
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=Contractor Marketplace
VITE_ENABLE_ANALYTICS=false
```

---

## 📁 Folder Structure

```
src/
├── components/              # Reusable React components
│   ├── ui/                 # Base UI components (shadcn/ui)
│   ├── dashboard/          # Dashboard-specific components
│   ├── forms/              # Form components
│   └── layout/             # Layout components
├── pages/                  # Route/page components
│   ├── auth/              # Authentication pages
│   ├── dashboard/         # Dashboard pages
│   └── public/            # Public pages
├── store/                  # Redux state management
│   ├── slices/            # Redux slices
│   ├── selectors/         # Memoized selectors
│   └── middleware/        # Custom middleware
├── services/              # API service layer
├── types/                 # TypeScript type definitions
├── hooks/                 # Custom React hooks
├── utils/                 # Utility functions
├── data/                  # Static data and constants
├── lib/                   # Third-party library configurations
├── App.tsx                # Root component
├── main.tsx               # Application entry point
└── index.css              # Global styles
```
---

## 🎨 Core Features

### 1. Home Page (`src/pages/Index.tsx`)
**Purpose**: Landing page showcasing platform features

**Components Used**:
- `HeroSection` - Main banner with call-to-action
- `AboutSection` - Company overview
- `FeaturesSection` - Platform features grid
- `ServicesSection` - Services showcase
- `TestimonialsSection` - Client testimonials
- `StatsSection` - Platform statistics
- `CTASection` - Call-to-action sections

**Key Features**:
- Responsive hero banner
- Feature highlights with icons
- Client testimonials carousel
- Statistics counter animations
- Newsletter signup form

### 2. Contractor Discovery (`src/pages/Contractors.tsx`)
**Purpose**: Search and browse contractors

**Components Used**:
- `AdvancedSearchBar` - Search with filters
- `CompanyCard` - Contractor listing cards
- `ProjectTypeSelector` - Filter by project type

**Key Features**:
- Advanced search with multiple filters
- Contractor cards with ratings and reviews
- Pagination for large result sets
- Featured contractors section
- Location-based filtering

**Search Filters**:
- Location (city, state, zip)
- Service type (plumbing, electrical, etc.)
- Rating (minimum star rating)
- Years of experience
- Certification status
- Project size

### 3. Contractor Details (`src/pages/ContractorDetails.tsx`)
**Purpose**: Detailed contractor profile page

**Key Features**:
- **Image Gallery** - Swiper-powered project showcase
- **Company Information** - Detailed business profile
- **Certifications & Awards** - Professional credentials
- **Services Offered** - Comprehensive service list
- **Client Reviews** - Detailed testimonials with ratings
- **Contact Options** - Phone, email, website buttons
- **Service Areas** - Geographic coverage map

**Data Structure**:
```typescript
interface ContractorDetail {
  id: number;
  name: string;
  rating: number;
  reviewCount: number;
  yearsInBusiness: number;
  description: string;
  certifications: string[];
  awards: string[];
  services: string[];
  specialties: string[];
  serviceAreas: string[];
  images: string[];
  testimonials: Testimonial[];
  contact: ContactInfo;
}
```

### 4. Authentication System
**Pages**:
- `Login.tsx` - User login
- `Signup.tsx` - User registration  
- `SignupMultiStep.tsx` - Multi-step registration
- `ForgotPassword.tsx` - Password recovery
- `ResetPassword.tsx` - Password reset
- `VerifyEmail.tsx` - Email verification

**Features**:
- Form validation with Zod schemas
- Redux state management
- Persistent sessions
- Role-based access control
- Password strength validation
- Email verification flow

### 5. Dashboard System
**Role-Based Dashboards**:
- `GCDashboard.tsx` - General Contractor dashboard
- `SubcontractorDashboard.tsx` - Subcontractor dashboard
- `SupplierDashboard.tsx` - Supplier dashboard
- `HomeownerDashboard.tsx` - Homeowner dashboard

**Common Features**:
- Overview statistics
- Recent activity feed
- Quick action buttons
- Profile management
- Settings access
- Notification center

### 6. AI Chatbot (`src/components/AIChatbot.tsx`)
**Purpose**: Intelligent assistant for user queries

**Features**:
- Real-time messaging interface
- Context-aware responses
- Redux state integration
- Message history persistence
- Typing indicators
- Mobile-responsive design

**State Management**:
```typescript
interface ChatbotState {
  messages: Message[];
  isOpen: boolean;
  isTyping: boolean;
  context: string;
}
```

### 7. Service & Product Catalog
**Pages**:
- `Services.tsx` - Service listings
- `ServiceDetail.tsx` - Individual service details
- `Products.tsx` - Product showcase
- AI-powered tools:
  - `AIQuantityTakeOff.tsx`
  - `AICostEstimation.tsx`
  - `AIVirtualAssistant.tsx`

---

## 🗄️ State Management

### Redux Store Architecture

**Store Configuration** (`src/store/index.ts`):
```typescript
export const store = configureStore({
  reducer: {
    auth: authSlice.reducer,
    contractors: contractorSlice.reducer,
    chatbot: chatbotSlice.reducer,
    ui: uiSlice.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: {
        ignoredActions: [FLUSH, REHYDRATE, PAUSE, PERSIST, PURGE, REGISTER],
      },
    }).concat(persistMiddleware),
});
```

### Redux Slices

#### 1. Auth Slice (`src/store/slices/authSlice.ts`)
**Purpose**: Manage user authentication state

**State Structure**:
```typescript
interface AuthState {
  user: User | null;
  token: string | null;
  isAuthenticated: boolean;
  loading: boolean;
  error: string | null;
}
```

**Actions**:
- `loginUser(credentials)` - Async login
- `registerUser(userData)` - Async registration
- `logout()` - Clear auth state
- `setUser(user)` - Set user data
- `clearError()` - Clear error messages

**Usage Example**:
```typescript
import { useAppDispatch, useAppSelector } from '@/store/hooks';
import { loginUser } from '@/store/slices/authSlice';

const dispatch = useAppDispatch();
const { user, loading, error } = useAppSelector(state => state.auth);

const handleLogin = async (credentials: LoginData) => {
  try {
    await dispatch(loginUser(credentials)).unwrap();
    // Handle success
  } catch (error) {
    // Handle error
  }
};
```

#### 2. Contractor Slice (`src/store/slices/contractorSlice.ts`)
**Purpose**: Manage contractor data and search

**State Structure**:
```typescript
interface ContractorState {
  contractors: Contractor[];
  filteredContractors: Contractor[];
  selectedContractor: Contractor | null;
  filters: ContractorFilters;
  searchQuery: string;
  loading: boolean;
  error: string | null;
  pagination: PaginationState;
}
```

**Actions**:
- `fetchContractors()` - Load contractors
- `searchContractors(query)` - Search functionality
- `setFilters(filters)` - Apply filters
- `selectContractor(id)` - Select contractor
- `clearFilters()` - Reset filters

#### 3. Chatbot Slice (`src/store/slices/chatbotSlice.ts`)
**Purpose**: Manage AI chatbot state

**State Structure**:
```typescript
interface ChatbotState {
  messages: Message[];
  isOpen: boolean;
  isTyping: boolean;
  context: string;
}
```

**Actions**:
- `sendMessage(message)` - Send user message
- `receiveMessage(message)` - Receive AI response
- `toggleChatbot()` - Open/close chatbot
- `clearMessages()` - Clear chat history

### Selectors (`src/store/selectors/`)

**Memoized Selectors** for performance optimization:
```typescript
// contractorSelectors.ts
export const selectFilteredContractors = createSelector(
  [selectContractors, selectFilters, selectSearchQuery],
  (contractors, filters, searchQuery) => {
    return contractors.filter(contractor => {
      // Apply filters and search logic
      return matchesFilters(contractor, filters) && 
             matchesSearch(contractor, searchQuery);
    });
  }
);

export const selectTopRatedContractors = createSelector(
  [selectContractors],
  (contractors) => contractors
    .filter(c => c.rating >= 4.5)
    .sort((a, b) => b.rating - a.rating)
    .slice(0, 10)
);
```

---

## 🛣️ Routing System

### Route Configuration (`src/App.tsx`)

**Public Routes**:
```typescript
// Home & Marketing
<Route path="/" element={<Index />} />
<Route path="/about-us" element={<AboutUs />} />
<Route path="/contact-us" element={<ContactUs />} />
<Route path="/services" element={<Services />} />
<Route path="/services/:serviceName" element={<ServiceDetail />} />

// Contractors
<Route path="/contractors" element={<Contractors />} />
<Route path="/contractors/:id" element={<ContractorDetails />} />

// Authentication
<Route path="/login" element={<Login />} />
<Route path="/signup" element={<SignupMultiStep />} />
<Route path="/forgot-password" element={<ForgotPassword />} />
```

**Protected Routes**:
```typescript
// Dashboards (require authentication)
<Route path="/gc-dashboard/*" element={<GCDashboard />} />
<Route path="/subcontractor-dashboard/*" element={<SubcontractorDashboard />} />
<Route path="/supplier-dashboard/*" element={<SupplierDashboard />} />
<Route path="/homeowner-dashboard/*" element={<HomeownerDashboard />} />
<Route path="/settings" element={<Settings />} />
```

### Route Protection (`src/components/ProtectedRoute.tsx`)
```typescript
const ProtectedRoute: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const { isAuthenticated } = useAppSelector(state => state.auth);
  
  if (!isAuthenticated) {
    return <Navigate to="/login" replace />;
  }
  
  return <>{children}</>;
};
```

### Navigation Patterns
- **Programmatic Navigation**: `useNavigate()` hook
- **Link Components**: `<Link to="/path">` for internal navigation
- **Dynamic Routes**: URL parameters with `useParams()`
- **Query Parameters**: `useSearchParams()` for filters

---

## 🎨 UI Components

### Component Hierarchy

#### Base UI Components (`src/components/ui/`)
**shadcn/ui components** - Accessible, customizable primitives:

```typescript
// Button variants
<Button variant="default">Primary</Button>
<Button variant="secondary">Secondary</Button>
<Button variant="outline">Outline</Button>
<Button variant="ghost">Ghost</Button>

// Form components
<Input placeholder="Enter text" />
<Textarea placeholder="Enter description" />
<Select>
  <SelectTrigger>
    <SelectValue placeholder="Select option" />
  </SelectTrigger>
  <SelectContent>
    <SelectItem value="option1">Option 1</SelectItem>
  </SelectContent>
</Select>

// Feedback components
<Alert>
  <AlertTitle>Alert Title</AlertTitle>
  <AlertDescription>Alert description</AlertDescription>
</Alert>

<Toast>
  <ToastTitle>Success!</ToastTitle>
  <ToastDescription>Operation completed</ToastDescription>
</Toast>
```

#### Feature Components (`src/components/`)

**Layout Components**:
- `ReduxHeader.tsx` - Navigation header with auth state
- `Footer.tsx` - Site footer with links
- `Sidebar.tsx` - Dashboard sidebar navigation

**Home Page Components**:
- `HeroSection.tsx` - Landing page hero
- `FeaturesSection.tsx` - Feature showcase grid
- `TestimonialsSection.tsx` - Client testimonials carousel
- `StatsSection.tsx` - Animated statistics
- `CTASection.tsx` - Call-to-action sections

**Contractor Components**:
- `CompanyCard.tsx` - Contractor listing card
- `ContractorCard.tsx` - Individual contractor card
- `AdvancedSearchBar.tsx` - Search with filters
- `ProjectTypeSelector.tsx` - Project type filter

**Utility Components**:
- `AIChatbot.tsx` - AI assistant interface
- `NotificationSystem.tsx` - Toast notifications
- `LoadingSpinner.tsx` - Loading indicators

### Component Design Patterns

#### 1. Compound Components
```typescript
// Card component with sub-components
<Card>
  <CardHeader>
    <CardTitle>Title</CardTitle>
    <CardDescription>Description</CardDescription>
  </CardHeader>
  <CardContent>
    Content goes here
  </CardContent>
  <CardFooter>
    <Button>Action</Button>
  </CardFooter>
</Card>
```

#### 2. Render Props Pattern
```typescript
<DataFetcher
  render={({ data, loading, error }) => (
    loading ? <LoadingSpinner /> :
    error ? <ErrorMessage error={error} /> :
    <DataDisplay data={data} />
  )}
/>
```

#### 3. Custom Hooks Pattern
```typescript
// Custom hook for contractor data
const useContractor = (id: string) => {
  const dispatch = useAppDispatch();
  const contractor = useAppSelector(state => 
    selectContractorById(state, id)
  );
  
  useEffect(() => {
    if (!contractor) {
      dispatch(fetchContractorById(id));
    }
  }, [id, contractor, dispatch]);
  
  return contractor;
};
```

### Styling Approach

#### Tailwind CSS Utility Classes
```typescript
// Responsive design
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  
// Flexbox layouts
<div className="flex items-center justify-between p-4">

// Hover states
<button className="bg-blue-500 hover:bg-blue-600 transition-colors">

// Dark mode support
<div className="bg-white dark:bg-gray-800 text-gray-900 dark:text-white">
```

#### Component Variants with CVA
```typescript
import { cva } from "class-variance-authority";

const buttonVariants = cva(
  "inline-flex items-center justify-center rounded-md font-medium transition-colors",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground hover:bg-primary/90",
        secondary: "bg-secondary text-secondary-foreground hover:bg-secondary/80",
        outline: "border border-input hover:bg-accent hover:text-accent-foreground",
      },
      size: {
        default: "h-10 px-4 py-2",
        sm: "h-9 rounded-md px-3",
        lg: "h-11 rounded-md px-8",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
);
```

---

## 🔌 API Integration

### Service Layer Architecture

#### Base API Configuration (`src/services/api.ts`)
```typescript
const api = axios.create({
  baseURL: import.meta.env.VITE_API_URL,
  headers: { 'Content-Type': 'application/json' },
  timeout: 30000,
});

// Request interceptor - adds auth token
api.interceptors.request.use((config) => {
  const token = localStorage.getItem('token');
  if (token) {
    config.headers.Authorization = `Bearer ${token}`;
  }
  return config;
});

// Response interceptor - handles errors
api.interceptors.response.use(
  (response) => response,
  (error) => {
    if (error.response?.status === 401) {
      // Handle token expiration
      handleLogout();
    }
    return Promise.reject(error);
  }
);
```

#### Service Classes

**Auth Service** (`src/services/authService.ts`):
```typescript
class AuthService {
  async login(data: LoginData): Promise<ApiResponse<AuthResponse>> {
    const response = await api.post('/auth/login', data);
    
    if (response.data.success) {
      localStorage.setItem('token', response.data.data.token);
      localStorage.setItem('user', JSON.stringify(response.data.data.user));
    }
    
    return response.data;
  }

  async register(data: RegisterData): Promise<ApiResponse<AuthResponse>> {
    const response = await api.post('/auth/register', data);
    return response.data;
  }

  async getProfile(): Promise<ApiResponse<User>> {
    const response = await api.get('/auth/profile');
    return response.data;
  }
}

export default new AuthService();
```

**Contractor Service** (`src/services/contractorService.ts`):
```typescript
class ContractorService {
  async getContractors(params?: ContractorFilters): Promise<PaginatedResponse<Contractor>> {
    const response = await api.get('/contractors', { params });
    return response.data;
  }

  async getContractorById(id: number): Promise<ApiResponse<ContractorDetail>> {
    const response = await api.get(`/contractors/${id}`);
    return response.data;
  }

  async searchContractors(query: string): Promise<ApiResponse<Contractor[]>> {
    const response = await api.get(`/contractors/search?q=${query}`);
    return response.data;
  }
}

export default new ContractorService();
```

### Type Definitions (`src/types/`)

**API Types** (`src/types/api.types.ts`):
```typescript
export interface ApiResponse<T = any> {
  success: boolean;
  message: string;
  data: T;
}

export interface PaginatedResponse<T> {
  success: boolean;
  data: T[];
  pagination: {
    page: number;
    limit: number;
    total: number;
    totalPages: number;
  };
}
```

**Auth Types** (`src/types/auth.types.ts`):
```typescript
export interface User {
  id: number;
  name: string;
  email: string;
  role: 'client' | 'contractor' | 'admin';
  phone?: string;
  avatar?: string;
  verified: boolean;
}

export interface LoginData {
  email: string;
  password: string;
  rememberMe?: boolean;
}

export interface RegisterData {
  name: string;
  email: string;
  password: string;
  confirmPassword: string;
  role: 'client' | 'contractor';
  phone?: string;
}
```

### Integration with Redux

**Async Thunks** for API calls:
```typescript
export const loginUser = createAsyncThunk(
  'auth/login',
  async (credentials: LoginData, { rejectWithValue }) => {
    try {
      const response = await authService.login(credentials);
      return response.data;
    } catch (error: any) {
      return rejectWithValue(error.message);
    }
  }
);

export const fetchContractors = createAsyncThunk(
  'contractors/fetchContractors',
  async (filters?: ContractorFilters) => {
    const response = await contractorService.getContractors(filters);
    return response.data;
  }
);
```

**Usage in Components**:
```typescript
const LoginForm = () => {
  const dispatch = useAppDispatch();
  const { loading, error } = useAppSelector(state => state.auth);

  const handleSubmit = async (data: LoginData) => {
    try {
      await dispatch(loginUser(data)).unwrap();
      navigate('/dashboard');
    } catch (error) {
      toast.error('Login failed');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      {/* Form fields */}
    </form>
  );
};
```

---

## 🔐 Authentication Flow

### Authentication Architecture

#### 1. Login Process
```
User enters credentials
       ↓
Form validation (Zod)
       ↓
Dispatch loginUser action
       ↓
API call to /auth/login
       ↓
Store token & user data
       ↓
Update Redux state
       ↓
Redirect to dashboard
```

#### 2. Token Management
```typescript
// Token storage
localStorage.setItem('token', response.data.token);
localStorage.setItem('refreshToken', response.data.refreshToken);

// Automatic token inclusion
api.interceptors.request.use((config) => {
  const token = localStorage.getItem('token');
  if (token) {
    config.headers.Authorization = `Bearer ${token}`;
  }
  return config;
});

// Token expiration handling
api.interceptors.response.use(
  (response) => response,
  async (error) => {
    if (error.response?.status === 401) {
      // Try to refresh token
      const refreshToken = localStorage.getItem('refreshToken');
      if (refreshToken) {
        // Implement token refresh logic
      } else {
        // Logout user
        handleLogout();
      }
    }
    return Promise.reject(error);
  }
);
```

#### 3. Route Protection
```typescript
const ProtectedRoute: React.FC<{ children: React.ReactNode }> = ({ children }) => {
  const { isAuthenticated, loading } = useAppSelector(state => state.auth);
  
  if (loading) {
    return <LoadingSpinner />;
  }
  
  if (!isAuthenticated) {
    return <Navigate to="/login" replace />;
  }
  
  return <>{children}</>;
};

// Usage
<Route 
  path="/dashboard" 
  element={
    <ProtectedRoute>
      <Dashboard />
    </ProtectedRoute>
  } 
/>
```

#### 4. Role-Based Access
```typescript
const RoleProtectedRoute: React.FC<{
  children: React.ReactNode;
  allowedRoles: string[];
}> = ({ children, allowedRoles }) => {
  const { user } = useAppSelector(state => state.auth);
  
  if (!user || !allowedRoles.includes(user.role)) {
    return <Navigate to="/unauthorized" replace />;
  }
  
  return <>{children}</>;
};

// Usage
<RoleProtectedRoute allowedRoles={['contractor', 'admin']}>
  <ContractorDashboard />
</RoleProtectedRoute>
```

### Authentication Components

#### Login Form (`src/pages/Login.tsx`)
```typescript
const Login = () => {
  const dispatch = useAppDispatch();
  const navigate = useNavigate();
  const { loading, error } = useAppSelector(state => state.auth);

  const form = useForm<LoginData>({
    resolver: zodResolver(loginSchema),
    defaultValues: {
      email: '',
      password: '',
      rememberMe: false,
    },
  });

  const onSubmit = async (data: LoginData) => {
    try {
      await dispatch(loginUser(data)).unwrap();
      toast.success('Login successful!');
      navigate('/dashboard');
    } catch (error: any) {
      toast.error(error.message || 'Login failed');
    }
  };

  return (
    <Form {...form}>
      <form onSubmit={form.handleSubmit(onSubmit)}>
        <FormField
          control={form.control}
          name="email"
          render={({ field }) => (
            <FormItem>
              <FormLabel>Email</FormLabel>
              <FormControl>
                <Input type="email" {...field} />
              </FormControl>
              <FormMessage />
            </FormItem>
          )}
        />
        
        <FormField
          control={form.control}
          name="password"
          render={({ field }) => (
            <FormItem>
              <FormLabel>Password</FormLabel>
              <FormControl>
                <Input type="password" {...field} />
              </FormControl>
              <FormMessage />
            </FormItem>
          )}
        />
        
        <Button type="submit" disabled={loading}>
          {loading ? 'Signing in...' : 'Sign In'}
        </Button>
      </form>
    </Form>
  );
};
```

#### Registration Form (`src/pages/SignupMultiStep.tsx`)
Multi-step registration with form validation:

**Step 1**: Basic Information
- Name, Email, Password
- Password confirmation
- Terms acceptance

**Step 2**: Role Selection
- Client or Contractor
- Role-specific fields

**Step 3**: Profile Details
- Phone number
- Location
- Company information (for contractors)

**Step 4**: Verification
- Email verification
- Account activation

---

## 🛠️ Development Guidelines

### Code Organization

#### Component Structure
```typescript
// 1. Imports (external first, then internal)
import React, { useState, useEffect } from 'react';
import { useNavigate } from 'react-router-dom';
import { useAppDispatch, useAppSelector } from '@/store/hooks';
import { Button } from '@/components/ui/button';

// 2. Types/Interfaces
interface ComponentProps {
  title: string;
  onAction: () => void;
}

// 3. Component
export const MyComponent: React.FC<ComponentProps> = ({ title, onAction }) => {
  // 4. Hooks (state, effects, custom hooks)
  const [loading, setLoading] = useState(false);
  const navigate = useNavigate();
  const dispatch = useAppDispatch();
  const data = useAppSelector(state => state.data);

  // 5. Event handlers
  const handleClick = async () => {
    setLoading(true);
    try {
      await onAction();
    } finally {
      setLoading(false);
    }
  };

  // 6. Effects
  useEffect(() => {
    // Side effects
  }, []);

  // 7. Render
  return (
    <div className="p-4">
      <h1 className="text-2xl font-bold">{title}</h1>
      <Button onClick={handleClick} disabled={loading}>
        {loading ? 'Loading...' : 'Click Me'}
      </Button>
    </div>
  );
};
```

#### Naming Conventions

**Files & Folders**:
- Components: `PascalCase.tsx` (e.g., `ContractorCard.tsx`)
- Pages: `PascalCase.tsx` (e.g., `ContractorDetails.tsx`)
- Utilities: `camelCase.ts` (e.g., `formatDate.ts`)
- Hooks: `use-kebab-case.ts` (e.g., `use-contractor.ts`)
- Types: `kebab-case.types.ts` (e.g., `contractor.types.ts`)

**Variables & Functions**:
- Constants: `UPPER_SNAKE_CASE`
- Functions: `camelCase`
- Components: `PascalCase`
- Props: `camelCase`
- Types/Interfaces: `PascalCase`

**Redux**:
- Slices: `featureSlice.ts`
- Actions: `actionName`
- Selectors: `selectFeature`
- Thunks: `fetchFeature`

### TypeScript Best Practices

#### 1. Strict Type Definitions
```typescript
// ✅ Good - Specific types
interface User {
  id: number;
  name: string;
  email: string;
  role: 'client' | 'contractor' | 'admin';
}

// ❌ Avoid - Generic types
interface User {
  id: any;
  name: any;
  email: any;
  role: string;
}
```

#### 2. Generic Components
```typescript
interface ListProps<T> {
  items: T[];
  renderItem: (item: T) => React.ReactNode;
  keyExtractor: (item: T) => string | number;
}

function List<T>({ items, renderItem, keyExtractor }: ListProps<T>) {
  return (
    <ul>
      {items.map(item => (
        <li key={keyExtractor(item)}>
          {renderItem(item)}
        </li>
      ))}
    </ul>
  );
}
```

#### 3. Utility Types
```typescript
// Pick specific properties
type UserSummary = Pick<User, 'id' | 'name' | 'email'>;

// Make properties optional
type PartialUser = Partial<User>;

// Exclude properties
type UserWithoutId = Omit<User, 'id'>;

// Create unions
type UserRole = User['role'];
```

### Performance Optimization

#### 1. Component Memoization
```typescript
// Memo for expensive components
const ExpensiveComponent = React.memo(({ data }) => {
  return <div>{/* Expensive rendering */}</div>;
});

// Memo with custom comparison
const OptimizedComponent = React.memo(({ user, settings }) => {
  return <div>{/* Component content */}</div>;
}, (prevProps, nextProps) => {
  return prevProps.user.id === nextProps.user.id &&
         prevProps.settings.theme === nextProps.settings.theme;
});
```

#### 2. Hook Optimization
```typescript
// useMemo for expensive calculations
const expensiveValue = useMemo(() => {
  return heavyCalculation(data);
}, [data]);

// useCallback for stable function references
const handleClick = useCallback((id: string) => {
  onItemClick(id);
}, [onItemClick]);

// Custom hooks for reusable logic
const useContractorData = (id: string) => {
  const [contractor, setContractor] = useState<Contractor | null>(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetchContractor(id).then(setContractor).finally(() => setLoading(false));
  }, [id]);

  return { contractor, loading };
};
```

#### 3. Code Splitting
```typescript
// Lazy load pages
const Dashboard = lazy(() => import('./pages/Dashboard'));
const ContractorDetails = lazy(() => import('./pages/ContractorDetails'));

// Suspense wrapper
<Suspense fallback={<LoadingSpinner />}>
  <Routes>
    <Route path="/dashboard" element={<Dashboard />} />
    <Route path="/contractors/:id" element={<ContractorDetails />} />
  </Routes>
</Suspense>
```

### Error Handling

#### 1. Error Boundaries
```typescript
class ErrorBoundary extends React.Component<
  { children: React.ReactNode },
  { hasError: boolean }
> {
  constructor(props: any) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error: Error) {
    return { hasError: true };
  }

  componentDidCatch(error: Error, errorInfo: React.ErrorInfo) {
    console.error('Error caught by boundary:', error, errorInfo);
  }

  render() {
    if (this.state.hasError) {
      return <ErrorFallback />;
    }

    return this.props.children;
  }
}
```

#### 2. API Error Handling
```typescript
const useApiCall = <T>(apiCall: () => Promise<T>) => {
  const [data, setData] = useState<T | null>(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  const execute = async () => {
    setLoading(true);
    setError(null);
    
    try {
      const result = await apiCall();
      setData(result);
    } catch (err: any) {
      setError(err.message || 'An error occurred');
    } finally {
      setLoading(false);
    }
  };

  return { data, loading, error, execute };
};
```

### Testing Strategy

#### 1. Component Testing
```typescript
import { render, screen, fireEvent } from '@testing-library/react';
import { Provider } from 'react-redux';
import { store } from '@/store';
import { Button } from '@/components/ui/button';

describe('Button Component', () => {
  it('renders with correct text', () => {
    render(<Button>Click me</Button>);
    expect(screen.getByText('Click me')).toBeInTheDocument();
  });

  it('calls onClick when clicked', () => {
    const handleClick = jest.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    fireEvent.click(screen.getByText('Click me'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
});
```

#### 2. Redux Testing
```typescript
import { configureStore } from '@reduxjs/toolkit';
import authSlice, { loginUser } from '@/store/slices/authSlice';

describe('Auth Slice', () => {
  let store: any;

  beforeEach(() => {
    store = configureStore({
      reducer: { auth: authSlice.reducer },
    });
  });

  it('should handle login success', async () => {
    const credentials = { email: 'test@example.com', password: 'password' };
    
    await store.dispatch(loginUser(credentials));
    
    const state = store.getState().auth;
    expect(state.isAuthenticated).toBe(true);
    expect(state.user).toBeDefined();
  });
});
```

---

## 🚀 Build & Deployment

### Build Process

#### Development Build
```bash
npm run dev
```
**Features**:
- Hot Module Replacement (HMR)
- Fast refresh
- Source maps
- Development mode optimizations
- Proxy configuration for API calls

#### Production Build
```bash
npm run build
```
**Process**:
1. TypeScript compilation
2. Code minification and compression
3. Tree shaking (remove unused code)
4. Asset optimization (images, fonts)
5. CSS purging (remove unused styles)
6. Bundle splitting and lazy loading

**Output Structure**:
```
dist/
├── assets/
│   ├── index-[hash].js      # Main JavaScript bundle
│   ├── index-[hash].css     # Main CSS bundle
│   ├── vendor-[hash].js     # Third-party libraries
│   └── [component]-[hash].js # Lazy-loaded components
├── images/                  # Optimized images
└── index.html               # Entry HTML file
```

### Environment Configuration

#### Environment Files
```bash
.env                    # Default environment variables
.env.local             # Local overrides (gitignored)
.env.development       # Development environment
.env.production        # Production environment
```

#### Environment Variables
```env
# API Configuration
VITE_API_URL=https://api.contractormarketplace.com/api
VITE_APP_NAME=Contractor Marketplace
VITE_APP_VERSION=1.0.0

# Feature Flags
VITE_ENABLE_ANALYTICS=true
VITE_ENABLE_CHATBOT=true
VITE_ENABLE_NOTIFICATIONS=true

# Third-party Services
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_key
VITE_STRIPE_PUBLISHABLE_KEY=your_stripe_key
VITE_SENTRY_DSN=your_sentry_dsn
```

### Deployment Options

#### 1. Vercel (Recommended)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

**Configuration** (`vercel.json`):
```json
{
  "framework": "vite",
  "buildCommand": "npm run build",
  "outputDirectory": "dist",
  "rewrites": [
    {
      "source": "/api/(.*)",
      "destination": "https://your-api-domain.com/api/$1"
    },
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

#### 2. Netlify
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod --dir=dist
```

**Configuration** (`netlify.toml`):
```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/api/*"
  to = "https://your-api-domain.com/api/:splat"
  status = 200

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

#### 3. AWS S3 + CloudFront
```bash
# Build the project
npm run build

# Upload to S3
aws s3 sync dist/ s3://your-bucket-name --delete

# Invalidate CloudFront cache
aws cloudfront create-invalidation --distribution-id YOUR_DISTRIBUTION_ID --paths "/*"
```

#### 4. Docker Deployment
```dockerfile
# Dockerfile
FROM node:18-alpine as builder

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### Performance Optimization

#### 1. Bundle Analysis
```bash
# Analyze bundle size
npm run build -- --analyze

# Or use webpack-bundle-analyzer
npx webpack-bundle-analyzer dist/assets/*.js
```

#### 2. Code Splitting Strategies
```typescript
// Route-based splitting
const Dashboard = lazy(() => import('./pages/Dashboard'));
const ContractorDetails = lazy(() => import('./pages/ContractorDetails'));

// Component-based splitting
const HeavyComponent = lazy(() => import('./components/HeavyComponent'));

// Library splitting
const Chart = lazy(() => import('./components/Chart'));
```

#### 3. Asset Optimization
```typescript
// Image optimization
import { defineConfig } from 'vite';

export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        assetFileNames: (assetInfo) => {
          const info = assetInfo.name.split('.');
          const ext = info[info.length - 1];
          if (/png|jpe?g|svg|gif|tiff|bmp|ico/i.test(ext)) {
            return `images/[name]-[hash][extname]`;
          }
          return `assets/[name]-[hash][extname]`;
        },
      },
    },
  },
});
```

#### 4. Caching Strategy
```typescript
// Service Worker for caching
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}

// HTTP caching headers
// Set in your deployment configuration
Cache-Control: public, max-age=31536000  // Static assets
Cache-Control: no-cache                  // HTML files
```

---

## 📊 Performance Optimization

### Core Web Vitals

#### 1. Largest Contentful Paint (LCP)
**Target**: < 2.5 seconds

**Optimizations**:
- Image optimization and lazy loading
- Critical CSS inlining
- Resource preloading
- CDN usage

```typescript
// Image lazy loading
<img 
  src={imageSrc} 
  loading="lazy" 
  alt="Description"
  className="w-full h-auto"
/>

// Resource preloading
<link rel="preload" href="/fonts/main.woff2" as="font" type="font/woff2" crossorigin />
```

#### 2. First Input Delay (FID)
**Target**: < 100 milliseconds

**Optimizations**:
- Code splitting
- Reduce JavaScript execution time
- Use web workers for heavy computations

```typescript
// Web worker for heavy calculations
const worker = new Worker('/workers/calculation.js');
worker.postMessage(data);
worker.onmessage = (e) => {
  setResult(e.data);
};
```

#### 3. Cumulative Layout Shift (CLS)
**Target**: < 0.1

**Optimizations**:
- Reserve space for images and ads
- Use CSS aspect-ratio
- Avoid inserting content above existing content

```css
/* Reserve space for images */
.image-container {
  aspect-ratio: 16 / 9;
}

/* Skeleton loading */
.skeleton {
  background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
  background-size: 200% 100%;
  animation: loading 1.5s infinite;
}
```

### React Performance

#### 1. Component Optimization
```typescript
// Memo for preventing unnecessary re-renders
const ContractorCard = React.memo(({ contractor, onSelect }) => {
  return (
    <div onClick={() => onSelect(contractor.id)}>
      {/* Card content */}
    </div>
  );
});

// useMemo for expensive calculations
const filteredContractors = useMemo(() => {
  return contractors.filter(contractor => 
    contractor.rating >= minRating &&
    contractor.location.includes(searchLocation)
  );
}, [contractors, minRating, searchLocation]);

// useCallback for stable function references
const handleContractorSelect = useCallback((id: string) => {
  navigate(`/contractors/${id}`);
}, [navigate]);
```

#### 2. Virtual Scrolling
```typescript
import { FixedSizeList as List } from 'react-window';

const ContractorList = ({ contractors }) => {
  const Row = ({ index, style }) => (
    <div style={style}>
      <ContractorCard contractor={contractors[index]} />
    </div>
  );

  return (
    <List
      height={600}
      itemCount={contractors.length}
      itemSize={200}
      width="100%"
    >
      {Row}
    </List>
  );
};
```

#### 3. Image Optimization
```typescript
// Progressive image loading
const ProgressiveImage = ({ src, placeholder, alt }) => {
  const [imageSrc, setImageSrc] = useState(placeholder);
  const [imageRef, setImageRef] = useState<HTMLImageElement>();

  useEffect(() => {
    const img = new Image();
    img.src = src;
    img.onload = () => {
      setImageSrc(src);
    };
    setImageRef(img);
  }, [src]);

  return (
    <img
      src={imageSrc}
      alt={alt}
      className={`transition-opacity duration-300 ${
        imageSrc === placeholder ? 'opacity-50' : 'opacity-100'
      }`}
    />
  );
};
```

### Bundle Optimization

#### 1. Tree Shaking
```typescript
// Import only what you need
import { debounce } from 'lodash-es';  // ✅ Good
import _ from 'lodash';                // ❌ Imports entire library

// Use dynamic imports for large libraries
const Chart = lazy(() => import('recharts').then(module => ({
  default: module.LineChart
})));
```

#### 2. Code Splitting
```typescript
// Route-based code splitting
const routes = [
  {
    path: '/dashboard',
    component: lazy(() => import('./pages/Dashboard')),
  },
  {
    path: '/contractors',
    component: lazy(() => import('./pages/Contractors')),
  },
];

// Feature-based code splitting
const AdminPanel = lazy(() => 
  import('./components/AdminPanel').then(module => ({
    default: module.AdminPanel
  }))
);
```

---

## 🧪 Testing Strategy

### Testing Pyramid

#### 1. Unit Tests (70%)
**Purpose**: Test individual components and functions

**Tools**: Jest, React Testing Library

```typescript
// Component testing
import { render, screen, fireEvent } from '@testing-library/react';
import { ContractorCard } from './ContractorCard';

describe('ContractorCard', () => {
  const mockContractor = {
    id: 1,
    name: 'Test Contractor',
    rating: 4.5,
    reviewCount: 10,
  };

  it('displays contractor information', () => {
    render(<ContractorCard contractor={mockContractor} />);
    
    expect(screen.getByText('Test Contractor')).toBeInTheDocument();
    expect(screen.getByText('4.5')).toBeInTheDocument();
    expect(screen.getByText('10 reviews')).toBeInTheDocument();
  });

  it('calls onSelect when clicked', () => {
    const onSelect = jest.fn();
    render(<ContractorCard contractor={mockContractor} onSelect={onSelect} />);
    
    fireEvent.click(screen.getByRole('button'));
    expect(onSelect).toHaveBeenCalledWith(mockContractor.id);
  });
});

// Utility function testing
import { formatCurrency } from './utils';

describe('formatCurrency', () => {
  it('formats currency correctly', () => {
    expect(formatCurrency(1234.56)).toBe('$1,234.56');
    expect(formatCurrency(0)).toBe('$0.00');
  });
});
```

#### 2. Integration Tests (20%)
**Purpose**: Test component interactions and API integration

```typescript
import { render, screen, waitFor } from '@testing-library/react';
import { Provider } from 'react-redux';
import { BrowserRouter } from 'react-router-dom';
import { store } from '@/store';
import { ContractorList } from './ContractorList';

const renderWithProviders = (component: React.ReactElement) => {
  return render(
    <Provider store={store}>
      <BrowserRouter>
        {component}
      </BrowserRouter>
    </Provider>
  );
};

describe('ContractorList Integration', () => {
  it('loads and displays contractors', async () => {
    renderWithProviders(<ContractorList />);
    
    expect(screen.getByText('Loading...')).toBeInTheDocument();
    
    await waitFor(() => {
      expect(screen.getByText('Test Contractor 1')).toBeInTheDocument();
      expect(screen.getByText('Test Contractor 2')).toBeInTheDocument();
    });
  });
});
```

#### 3. End-to-End Tests (10%)
**Purpose**: Test complete user workflows

**Tools**: Playwright, Cypress

```typescript
// Playwright E2E test
import { test, expect } from '@playwright/test';

test('user can search and view contractor details', async ({ page }) => {
  await page.goto('/');
  
  // Search for contractors
  await page.fill('[data-testid="search-input"]', 'plumber');
  await page.click('[data-testid="search-button"]');
  
  // Wait for results
  await expect(page.locator('[data-testid="contractor-card"]').first()).toBeVisible();
  
  // Click on first contractor
  await page.click('[data-testid="contractor-card"]');
  
  // Verify contractor details page
  await expect(page.locator('h1')).toContainText('Contractor Details');
  await expect(page.locator('[data-testid="contact-button"]')).toBeVisible();
});
```

### Testing Configuration

#### Jest Configuration (`jest.config.js`)
```javascript
module.exports = {
  testEnvironment: 'jsdom',
  setupFilesAfterEnv: ['<rootDir>/src/setupTests.ts'],
  moduleNameMapping: {
    '^@/(.*)$': '<rootDir>/src/$1',
  },
  collectCoverageFrom: [
    'src/**/*.{ts,tsx}',
    '!src/**/*.d.ts',
    '!src/main.tsx',
    '!src/vite-env.d.ts',
  ],
  coverageThreshold: {
    global: {
      branches: 80,
      functions: 80,
      lines: 80,
      statements: 80,
    },
  },
};
```

#### Test Setup (`src/setupTests.ts`)
```typescript
import '@testing-library/jest-dom';
import { server } from './mocks/server';

// Mock API server
beforeAll(() => server.listen());
afterEach(() => server.resetHandlers());
afterAll(() => server.close());

// Mock localStorage
const localStorageMock = {
  getItem: jest.fn(),
  setItem: jest.fn(),
  removeItem: jest.fn(),
  clear: jest.fn(),
};
global.localStorage = localStorageMock;
```

### Testing Best Practices

#### 1. Test Structure
```typescript
describe('Component/Feature Name', () => {
  // Setup
  beforeEach(() => {
    // Common setup
  });

  describe('when condition', () => {
    it('should do something', () => {
      // Arrange
      const props = { /* test props */ };
      
      // Act
      render(<Component {...props} />);
      
      // Assert
      expect(screen.getByText('Expected Text')).toBeInTheDocument();
    });
  });
});
```

#### 2. Testing Hooks
```typescript
import { renderHook, act } from '@testing-library/react';
import { useContractor } from './useContractor';

describe('useContractor', () => {
  it('fetches contractor data', async () => {
    const { result } = renderHook(() => useContractor('123'));
    
    expect(result.current.loading).toBe(true);
    
    await act(async () => {
      await waitFor(() => {
        expect(result.current.loading).toBe(false);
        expect(result.current.contractor).toBeDefined();
      });
    });
  });
});
```

#### 3. Mocking API Calls
```typescript
// Mock Service Worker (MSW)
import { rest } from 'msw';
import { setupServer } from 'msw/node';

const server = setupServer(
  rest.get('/api/contractors', (req, res, ctx) => {
    return res(
      ctx.json({
        success: true,
        data: [
          { id: 1, name: 'Test Contractor 1' },
          { id: 2, name: 'Test Contractor 2' },
        ],
      })
    );
  })
);

export { server };
```

---

## 📚 Summary

This frontend documentation covers a comprehensive React TypeScript application built with modern tools and best practices. The project features:

### ✅ **Production-Ready Architecture**
- **Type-safe** with full TypeScript coverage
- **Scalable** Redux state management
- **Modular** component architecture
- **Accessible** UI components with shadcn/ui
- **Responsive** mobile-first design

### ✅ **Modern Development Stack**
- React 18 with hooks and concurrent features
- Vite for fast development and optimized builds
- Tailwind CSS for utility-first styling
- Redux Toolkit for predictable state management
- React Router for client-side routing

### ✅ **Key Features Implemented**
- User authentication with role-based access
- Contractor search and discovery
- Detailed contractor profiles with reviews
- AI-powered chatbot assistance
- Responsive dashboard system
- Service and product catalogs

### ✅ **Developer Experience**
- Comprehensive TypeScript types
- Consistent code organization
- Reusable component library
- Automated testing setup
- Performance optimization
- Clear documentation

### 🚀 **Ready for Production**
The application is built with production deployment in mind, featuring optimized builds, environment configuration, and deployment guides for major platforms like Vercel, Netlify, and AWS.

This frontend provides a solid foundation for a contractor marketplace platform that can scale with business needs while maintaining code quality and developer productivity.