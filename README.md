# Senp.AI - Advanced AI Chat Platform

![Senp.AI Logo](/client/public/senpai-logo.png)

**Senp.AI** is a modern, feature-rich AI chat application that brings together the power of multiple AI providers in a sleek, user-friendly interface. With support for 8 different AI modes, 4 personality types, and 5 leading AI providers, Senp.AI offers an unparalleled conversational AI experience.

## ✨ Features

### 🤖 AI Modes
- **Unlimited**: Unrestricted AI with maximum capabilities
- **Genius**: Exceptional intelligence and deep analysis
- **Hacker**: Hacking mindset and unconventional thinking
- **Code**: Expert programming assistance
- **Research**: Deep research and academic insights
- **Creative**: Unlimited creative expression
- **Dark**: Powerful and comprehensive knowledge
- **Security**: Cybersecurity expertise

### 👤 Personality Types
- **Natural Human**: Friendly and conversational
- **Professional Expert**: Detailed and technical
- **Friendly Buddy**: Warm and encouraging
- **Genius**: Exceptional and innovative

### 🔌 Supported AI Providers
- **Groq**: Ultra-fast inference with Llama and Mixtral models
- **Google AI**: Gemini models with cutting-edge capabilities
- **OpenRouter**: Multi-model access with free options
- **Together AI**: Powerful distributed AI models
- **AI/ML API**: 200+ models including GPT-4, Claude, and more

### 🎨 Design Features
- **Dark & Light Themes**: Beautiful UI in both light and dark modes
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Smooth Animations**: Polished transitions and micro-interactions
- **Gradient Effects**: Modern gradient UI elements
- **Arabic & English**: Full bilingual support

### 💬 Chat Features
- **Message History**: Keep track of all conversations
- **Copy to Clipboard**: Easily copy AI responses
- **Export Chat**: Download conversations as text files
- **Clear Chat**: Start fresh conversations
- **Quick Actions**: Pre-built prompts for common tasks
- **Real-time Typing**: See when the AI is responding
- **Statistics**: Track questions asked and response times

### ⚙️ Advanced Settings
- **Temperature Control**: Adjust response creativity (0-2)
- **Token Limits**: Set maximum response length (100-8000)
- **Model Selection**: Choose from multiple models per provider
- **Provider Switching**: Switch between AI providers seamlessly
- **Streaming Support**: Enable/disable response streaming

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ and npm/pnpm
- A modern web browser

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/senpai-gpt.git
cd senpai-gpt
```

2. **Install dependencies**
```bash
npm install
# or
pnpm install
```

3. **Start the development server**
```bash
npm run dev
# or
pnpm dev
```

4. **Open in browser**
Navigate to `http://localhost:3000` to start using Senp.AI

## 🔑 API Keys Setup

To use Senp.AI, you'll need API keys from your preferred AI providers. The application currently includes demo keys, but for production use, you should add your own:

### Supported Providers
- **Groq**: Get your key from [console.groq.com](https://console.groq.com)
- **Google AI**: Get your key from [makersuite.google.com](https://makersuite.google.com)
- **OpenRouter**: Get your key from [openrouter.ai](https://openrouter.ai)
- **Together AI**: Get your key from [together.ai](https://together.ai)
- **AI/ML API**: Get your key from [aimlapi.com](https://aimlapi.com)

Update the API keys in `client/src/pages/Home.tsx`:
```typescript
const API_KEYS = {
  openrouter: 'your-key-here',
  groq: 'your-key-here',
  google: 'your-key-here',
  together: 'your-key-here',
  aimlapi: 'your-key-here'
};
```

## 📦 Build for Production

```bash
npm run build
# or
pnpm build
```

The production-ready files will be in the `dist/` directory.

## 🌐 Deploy to GitHub Pages

### 1. Create a GitHub Repository
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/senpai-gpt.git
git push -u origin main
```

### 2. Enable GitHub Pages
- Go to your repository settings
- Navigate to "Pages" section
- Select "Deploy from a branch"
- Choose `main` branch and `/root` folder
- Click "Save"

### 3. GitHub Actions (Optional)
The repository includes a GitHub Actions workflow for automatic deployment. The workflow will:
- Build the project on every push
- Deploy to GitHub Pages automatically

## 📁 Project Structure

```
senpai-gpt/
├── client/
│   ├── public/
│   │   └── senpai-logo.png      # Application logo
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Home.tsx         # Main chat interface
│   │   │   └── NotFound.tsx     # 404 page
│   │   ├── components/          # Reusable UI components
│   │   ├── contexts/            # React contexts
│   │   ├── lib/                 # Utility functions
│   │   ├── App.tsx              # Root component
│   │   ├── main.tsx             # Entry point
│   │   ├── index.css            # Global styles
│   │   └── const.ts             # Constants
│   ├── index.html               # HTML template
│   ├── tailwind.config.ts        # Tailwind configuration
│   └── tsconfig.json            # TypeScript configuration
├── server/                      # Backend placeholder
├── shared/                      # Shared types
├── package.json                 # Project dependencies
├── vite.config.ts               # Vite configuration
├── README.md                    # This file
├── LICENSE                      # MIT License
└── .gitignore                   # Git ignore rules
```

## 🎨 Customization

### Changing Colors
Edit `client/src/index.css` to modify the color scheme:
```css
@theme {
  --color-primary: #8b5cf6;
  --color-secondary: #ec4899;
  /* ... more colors ... */
}
```

### Changing Fonts
Update the font imports in `client/index.html`:
```html
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;900&display=swap" rel="stylesheet">
```

### Adding New AI Modes
Add a new mode object in `client/src/pages/Home.tsx`:
```typescript
newMode: {
  icon: IconComponent,
  name: 'Mode Name',
  gradient: 'from-color-500 to-color-500',
  desc: 'Description'
}
```

## 🔒 Security Notes

- **API Keys**: Never commit API keys to version control. Use environment variables in production.
- **CORS**: Some APIs may have CORS restrictions. Consider using a backend proxy for production.
- **Rate Limiting**: Be aware of rate limits for each provider.
- **Data Privacy**: User conversations are stored locally in the browser. No data is sent to external servers except API requests.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For issues, questions, or suggestions, please open an issue on GitHub.

## 🙏 Acknowledgments

- Built with [React 19](https://react.dev)
- Styled with [Tailwind CSS 4](https://tailwindcss.com)
- Icons from [Lucide React](https://lucide.dev)
- UI Components from [shadcn/ui](https://ui.shadcn.com)

## 🌟 Show Your Support

If you find Senp.AI useful, please consider giving it a star on GitHub!

---

**Made with ❤️ by the Senp.AI Team**
