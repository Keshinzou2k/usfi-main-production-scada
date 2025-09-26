# Advanced Production Control System

A comprehensive web-based production control dashboard for industrial batching operations, specifically designed for animal feed manufacturing with a focus on cock feed formulations.

## 🌟 Overview

The Advanced Production Control System is a sophisticated web application that manages and monitors industrial batching processes. It provides real-time control over mixing operations, formulation management, and production scheduling with an intuitive dashboard interface.

![Dashboard Preview](https://img.shields.io/badge/Status-Production_Ready-green)
![Technology](https://img.shields.io/badge/Technology-HTML5%2FCSS3%2FJavaScript-blue)

## 🚀 Key Features

### Production Management
- **Real-time Batch Control**: Monitor and control multiple mixers simultaneously
- **Smart Recipe Queue**: Priority-based assignment system with visual queue management
- **Automated Dispensing**: Loop-based dispensing algorithm with drop calculations
- **Weight Monitoring**: Real-time weight tracking with stability indicators

### Formulation System
- **22-Bin Inventory**: Comprehensive raw material management
- **Custom Recipes**: Predefined formulations for various animal feed types
- **Dynamic Formulation Table**: Real-time status updates for all bins
- **Drop-based Dispensing**: Intelligent material handling based on bin capacities

### User Interface
- **Responsive Design**: Optimized for various screen sizes
- **Multiple Themes**: Dark, Light, Traditional, and Soft color schemes
- **Interactive Controls**: Intuitive button-based interface for operators
- **Real-time Updates**: Live data refresh without page reload

### Maintenance & Safety
- **Fault Detection**: Comprehensive error handling and notification system
- **Emergency Stop**: Instant shutdown capability for safety
- **Maintenance Requests**: Structured request system for different departments
- **Production History**: Complete audit trail of all batches

## 🛠 Technology Stack

### Frontend
- **HTML5**: Semantic structure with modern web standards
- **CSS3**: Advanced styling with CSS Grid, Flexbox, and custom properties
- **JavaScript ES6+**: Vanilla JavaScript with modern features
- **Font Awesome**: Comprehensive icon library

### Key Libraries
- No external dependencies (pure vanilla implementation)
- Custom CSS framework with theme support
- Responsive design patterns

## 📋 Prerequisites

- Modern web browser (Chrome 80+, Firefox 75+, Safari 13+, Edge 80+)
- Web server for deployment (optional for local use)
- No database required (uses in-memory storage)

## 🚀 Installation & Setup

### Option 1: Direct File Access
```bash
# Clone or download the project
git clone <repository-url>
cd advanced-production-control

# Open the HTML file in your browser
open advance-production-control.html
```

### Option 2: Local Server
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

### Option 3: Production Deployment
1. Upload `advance-production-control.html` to your web server
2. Ensure proper MIME types are configured
3. Access via your domain: `https://yourdomain.com/advance-production-control.html`

## 📖 Usage Guide

### Starting a Production Batch
1. **Select Mixer**: Click on an available mixer (2, 3, or 4)
2. **Confirm Dispensing**: Review recipe details in the confirmation modal
3. **Monitor Progress**: Watch real-time updates in the formulation table
4. **Completion**: System automatically shows results upon completion

### Managing Recipes
- **Priority System**: Recipes with priority 2 are processed first
- **Batch Tracking**: System tracks remaining batches for each recipe
- **Mixer Assignment**: Automatic assignment based on batch size and priority

### Maintenance Features
- **Theme Selection**: Access via Settings → Theme
- **Maintenance Requests**: Use the structured form for issue reporting
- **Emergency Stop**: Immediate system shutdown for safety

## 🏗 System Architecture

### Data Structure
```javascript
{
  items: [
    {id: 1, name: "BARLEY", maxWeight: 150},
    // ... 21 more items
  ],
  recipes: [
    {
      id: "WARB7K",
      name: "WARBIRD 7 KINDS",
      priority: 1,
      batches: 8,
      mixer: 4,
      ingredients: [
        {itemId: 1, required: 150},
        // ... recipe components
      ]
    }
    // ... additional recipes
  ]
}
```

### State Management
The application uses a centralized state object (`appState`) that tracks:
- Current production status
- Timer and progress information
- Bin status and servo positions
- Active faults and error states
- Theme preferences

## 🔧 Configuration

### Theme Customization
The system supports four themes:
- **Dark** (Default): Industrial dark interface
- **Light**: High-contrast light mode
- **Traditional**: Warm, earthy tones
- **Soft**: Pastel color scheme

### Production Parameters
Key configurable parameters:
- Bulk servo position (default: 100%)
- Dribble servo position (default: 25%)
- Stability timeout (default: 30 seconds)
- Overshoot tolerance (default: 2%)

## 📊 Formulation Process

### Dispensing Algorithm
1. **Calculate Drops**: `Math.ceil(requiredWeight / binMaxWeight)`
2. **Bulk Phase**: 100% servo opening for rapid filling
3. **Dribble Phase**: 25% servo opening for precision
4. **Stability Check**: Wait for "ST" signal before transfer
5. **Weight Transfer**: Move from weigh bin to actual weight

### Status Indicators
- 🟢 **STANDBY**: Ready for operation
- 🔵 **DISPENSING**: Actively dispensing material
- 🟡 **CALIBRATING**: Waiting for weight stability
- 🟣 **DROPPING**: Transferring material
- 🔵 **DONE**: Process completed successfully
- 🔴 **OFFLINE**: System or bin unavailable

## 🚨 Safety Features

### Emergency Systems
- **E-Stop Function**: Immediate shutdown of all operations
- **Fault Detection**: Automatic error identification and logging
- **Safety Interlocks**: Prevents conflicting operations

### Error Handling
- **Overshoot Protection**: Monitors weight exceeding tolerances
- **Stability Timeout**: Prevents infinite waiting for signals
- **Retry Logic**: Automatic retry for minor faults

## 📱 Responsive Design

The interface adapts to different screen sizes:
- **Desktop**: Full dashboard with side-by-side panels
- **Tablet**: Stacked layout with optimized touch targets
- **Mobile**: Single-column design with larger controls

## 🔄 API & Integration

While currently a standalone application, the architecture supports future integration:
- REST API endpoints for recipe management
- WebSocket connections for real-time updates
- Export functionality for production reports

## 🧪 Testing

### Manual Testing Checklist
- [ ] Mixer selection and activation
- [ ] Recipe dispensing process
- [ ] Theme switching functionality
- [ ] Emergency stop procedures
- [ ] Maintenance request submission
- [ ] Responsive design across devices

## 📈 Performance Considerations

- **Client-Side Processing**: All calculations happen in-browser
- **Efficient DOM Updates**: Minimal re-rendering with targeted updates
- **Memory Management**: Automatic cleanup of completed processes
- **Optimized Animations**: CSS-based transitions for smooth performance

## 🔮 Future Enhancements

### Planned Features
- **User Authentication**: Role-based access control
- **Data Persistence**: Local storage or database integration
- **Advanced Analytics**: Production efficiency metrics
- **Multi-language Support**: Internationalization
- **API Integration**: ERP system connectivity

### Technical Roadmap
- Conversion to React/Vue.js component architecture
- Backend service with Node.js/Python
- Real-time collaboration features
- Mobile app development

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup
```bash
# Clone the repository
git clone https://github.com/yourusername/advanced-production-control.git

# Navigate to project directory
cd advanced-production-control

# Open in your preferred code editor
code .
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 🆘 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the documentation in the `/docs` folder
- Review common problems in the troubleshooting guide

## 🙏 Acknowledgments

- Icons provided by [Font Awesome](https://fontawesome.com)
- Color schemes inspired by modern industrial design principles
- Testing and feedback from production facility operators

---

**Note**: This is a simulation system designed for demonstration purposes. Always follow proper safety protocols when implementing industrial control systems in production environments.

---
<div align="center">
  
Made with ❤️ for industrial automation

![Version](https://img.shields.io/badge/Version-2.0.0-blue)
![Last Updated](https://img.shields.io/badge/Updated-September_2025-orange)

</div>
