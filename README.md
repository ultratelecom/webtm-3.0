# 🚀 Modern Next.js Template Stack

A cutting-edge, production-ready Next.js template featuring 3D graphics, animations, and modern web technologies. This template showcases the latest in web development with a beautiful interactive 3D demo page.

## ✨ Tech Stack

### 🎯 Core Framework
- **Next.js 15** - Latest React framework with App Router
- **React 19** - Latest React with concurrent features
- **TypeScript 5.8** - Advanced type safety and modern JS features

### 🎨 Styling & UI
- **Tailwind CSS 3.4** - Utility-first CSS framework
- **Shadcn/UI** - High-quality component library
- **Class Variance Authority** - Component variant management
- **Tailwind Merge & Variants** - Advanced utility management

### 🚀 3D & Animation
- **Three.js 0.177** - Powerful 3D graphics library
- **React Three Fiber 9.1** - React renderer for Three.js
- **@react-three/drei 10.3** - Useful helpers and abstractions
- **Framer Motion 12.20** - Production-ready animation library

### 🗄️ Backend & State
- **Supabase 2.50** - Complete backend platform (auth, database, storage)
- **Zustand 5.0** - Lightweight state management

### 🛠️ Development Tools
- **PostCSS & Autoprefixer** - CSS processing and optimization
- **Prettier 3.6** - Code formatting
- **ESLint 9.29** - Advanced linting and code quality

## 🏗️ Project Structure

```
src/
├── app/                    # Next.js App Router (v15)
│   ├── layout.tsx         # Root layout with metadata
│   ├── page.tsx          # Interactive 3D showcase homepage
│   └── globals.css       # Global styles with Tailwind
├── components/           # Reusable UI components
│   ├── Layout.tsx       # Main layout wrapper
│   ├── Audio/           # Audio recording components
│   ├── Comments/        # Comment system components
│   ├── Lesson/          # Educational components
│   ├── Admin/           # Admin dashboard components
│   └── PeerReview/      # Peer review system
├── lib/                 # Utilities and configuration
│   ├── utils.ts        # Helper functions
│   ├── supabase.ts     # Supabase client configuration
│   └── *.ts            # Mock data and utilities
└── styles/
    └── global.css      # Additional global styles
```

## 🚀 Getting Started

### Prerequisites
- **Node.js 18+** 
- **npm** or **yarn** or **pnpm**

### Installation

1. **Clone or download this template**
   ```bash
   git clone https://github.com/ultratelecom/webtm-3.0.git
   cd webtm-3.0
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:3000` to see the interactive 3D showcase

### Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build optimized production bundle
- `npm run start` - Start production server
- `npm run lint` - Run ESLint for code quality

## 🎯 What's Included

### ✅ Showcase Features
- **Interactive 3D Scene** - Live Three.js demo with geometric shapes
- **Smooth Animations** - Framer Motion powered page transitions
- **Responsive Design** - Beautiful on all device sizes
- **Modern Gradients** - Stunning visual effects with CSS
- **Glass Morphism** - Modern backdrop blur effects

### 🔧 Technical Features
- **TypeScript Setup** - Full type safety and IntelliSense
- **Component Architecture** - Modular, reusable components
- **3D Graphics Pipeline** - Ready-to-use Three.js integration
- **Animation System** - Framer Motion configuration
- **State Management** - Zustand store setup
- **Backend Ready** - Supabase integration configured

## 🎨 3D & Animation Showcase

The homepage demonstrates key capabilities:

### Three.js Scene
```tsx
function Scene() {
  return (
    <>
      <ambientLight intensity={0.5} />
      <pointLight position={[10, 10, 10]} />
      <mesh rotation={[0, 0, 0]}>
        <boxGeometry args={[2, 2, 2]} />
        <meshStandardMaterial color={'#8b5cf6'} />
      </mesh>
      {/* Additional 3D objects */}
      <OrbitControls enableZoom={false} />
    </>
  )
}
```

### Framer Motion Animations
```tsx
<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.8 }}
>
  {/* Animated content */}
</motion.div>
```

## 🗄️ Backend Integration

### Supabase Configuration
The template includes Supabase for:
- **Authentication** - User login/signup
- **Database** - PostgreSQL with real-time features
- **Storage** - File uploads and management
- **Edge Functions** - Serverless API endpoints

### Zustand State Management
```tsx
import { create } from 'zustand'

interface AppState {
  user: User | null
  setUser: (user: User) => void
}

export const useAppStore = create<AppState>((set) => ({
  user: null,
  setUser: (user) => set({ user }),
}))
```

## 🎨 Styling System

### Tailwind CSS Configuration
- **Custom Gradients** - Radial and conic gradients
- **Responsive Breakpoints** - Mobile-first design
- **Glass Morphism** - Modern backdrop effects
- **Color Palette** - Carefully selected color scheme

### Shadcn/UI Components
Pre-configured with:
- Button variants and sizes
- Form components
- Layout components
- Accessibility features

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm run build
```
Push to GitHub and connect to Vercel for automatic deployments.

### Other Platforms
- **Netlify** - Static site hosting
- **AWS Amplify** - Full-stack deployment
- **Railway** - Container deployment

### Environment Variables
```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_key
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

## 🔮 Extending the Template

### Adding New 3D Scenes
```tsx
import { Canvas } from '@react-three/fiber'
import { OrbitControls, Box, Sphere } from '@react-three/drei'

function CustomScene() {
  return (
    <Canvas>
      <ambientLight />
      <Box material-color="hotpink" />
      <Sphere args={[1, 32, 32]} material-color="orange" />
      <OrbitControls />
    </Canvas>
  )
}
```

### Database Schema (Supabase)
```sql
-- Example user profiles table
create table profiles (
  id uuid references auth.users on delete cascade,
  username text unique,
  avatar_url text,
  created_at timestamp with time zone default timezone('utc'::text, now())
);
```

### New Features to Add
1. **Authentication Pages** - Login/signup with Supabase Auth
2. **Dashboard** - User management interface
3. **File Upload** - Drag & drop with Supabase Storage
4. **Real-time Features** - Live collaboration with Supabase Realtime

## 📋 Best Practices

### Performance
- **Code Splitting** - Dynamic imports for large components
- **Image Optimization** - Next.js Image component
- **3D Optimization** - Efficient geometry and materials
- **Bundle Analysis** - Monitor build size

### Code Quality
- **TypeScript Strict Mode** - Enhanced type checking
- **ESLint Rules** - Consistent code style
- **Component Patterns** - Reusable and maintainable
- **Error Boundaries** - Graceful error handling

## 🧪 Testing Setup (Ready to Implement)

```bash
npm install --save-dev @testing-library/react @testing-library/jest-dom jest
npm install --save-dev @testing-library/user-event
```

## 📚 Documentation & Resources

### Framework Documentation
- [Next.js 15 Docs](https://nextjs.org/docs)
- [React 19 Features](https://react.dev/blog/2024/04/25/react-19)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)

### 3D Graphics
- [React Three Fiber](https://docs.pmnd.rs/react-three-fiber)
- [Three.js Documentation](https://threejs.org/docs/)
- [React Three Drei](https://github.com/pmndrs/drei)

### Styling & Animation
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Framer Motion](https://www.framer.com/motion/)
- [Shadcn/UI](https://ui.shadcn.com/)

### Backend
- [Supabase Docs](https://supabase.com/docs)
- [Zustand Guide](https://github.com/pmndrs/zustand)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Next.js Team](https://nextjs.org/) - Amazing React framework
- [Vercel](https://vercel.com/) - Deployment platform
- [Tailwind Labs](https://tailwindcss.com/) - CSS framework
- [Framer](https://www.framer.com/) - Animation library
- [Three.js](https://threejs.org/) - 3D graphics library
- [Supabase](https://supabase.com/) - Backend platform
- [Shadcn](https://ui.shadcn.com/) - Component library

---

**Ready to build the future of web? 🌟** 