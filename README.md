# 🏏 Crickounter

A modern, interactive cricket scoring application built with vanilla JavaScript. Track scores, manage overs, and enjoy a comprehensive cricket scoring experience with a sleek, mobile-first design.

## ✨ Features

### Core Functionality
- **Real-time Scoring**: Track runs, wickets, and overs in real-time
- **Complete Over Management**: Track individual balls, extras, and dismissals
- **Two Innings Support**: Full support for both innings with target tracking
- **Multiple Dismissal Types**: Caught, Bowled, Stumped, Run Out, Hit Wicket, and Others
- **Extras Handling**: Wide balls, No balls, Byes, and Leg byes
- **Match Setup**: Customizable overs per innings (T20, ODI, or custom)

### Advanced Features
- **Timeline View**: Visual timeline showing ball-by-ball progression
- **Target Tracking**: Required run rate and balls remaining calculations
- **Match Statistics**: Comprehensive stats including boundaries, dot balls, and extras
- **Undo Functionality**: Easily correct scoring mistakes
- **Auto-save**: Game state persists across browser sessions
- **Match Results**: Detailed match summaries and results

### User Experience
- **Dark/Light Theme**: Toggle between themes for comfortable viewing
- **Sound Effects**: Audio feedback for scoring actions (toggleable)
- **Fullscreen Mode**: Immersive scoring experience
- **Mobile Optimized**: Responsive design for all screen sizes
- **Keyboard Shortcuts**: Quick scoring with keyboard inputs
- **Touch Gestures**: Mobile-friendly touch interactions

### Visual Design
- **Modern UI**: Clean, professional interface with gradient designs
- **Animated Interactions**: Smooth animations and transitions
- **Visual Feedback**: Color-coded scoring elements and progress indicators
- **Celebration Effects**: Special animations for boundaries and match completion

## 🚀 Live Demo

Visit the live application: [https://crickounter.rajathverse.com/](https://crickounter.rajathverse.com/)

## 📁 Project Structure

```
crickounter/
├── scorecard.html          # Main application file
├── crickounter-site.yml    # AWS CloudFormation template
└── README.md              # Project documentation
```

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Storage**: Browser Local Storage for game persistence
- **Styling**: Custom CSS with CSS Variables for theming
- **Fonts**: Inter & JetBrains Mono from Google Fonts
- **Icons**: Font Awesome 6.4.0
- **Animations**: Canvas Confetti for celebrations
- **Screenshots**: HTML2Canvas for match summaries

## 🎯 How to Use

### Getting Started
1. Open the application in your web browser
2. Set up match parameters (overs per innings, players per team)
3. Start scoring by clicking the run buttons (0, 1, 2, 3, 4, 6)

### Scoring Actions
- **Runs**: Click number buttons (0-6) to add runs
- **Boundaries**: 4s and 6s trigger special celebrations
- **Extras**: Use "Wide" and "No Ball" buttons for extras
- **Dismissals**: Click "OUT" to select dismissal type
- **Rare Scores**: Access 5, 7, 8, 9 runs through "Rare buttons"

### Match Management
- **Undo**: Correct the last scoring action
- **Settings**: Adjust match parameters during the game
- **Theme**: Toggle between dark and light modes
- **Sound**: Enable/disable audio feedback
- **Fullscreen**: Enter fullscreen mode for better focus

### Innings Transition
- **End Innings**: Transition from first to second innings
- **Target Setting**: Automatically calculates target for second innings
- **Match Completion**: Displays detailed results and statistics

## ⚙️ AWS Infrastructure

The application is deployed using AWS CloudFormation with the following architecture:

### Components
- **S3 Bucket**: Static website hosting with public read access
- **CloudFront Distribution**: Global CDN for fast content delivery
- **Route 53**: DNS management for custom domain
- **ACM Certificate**: SSL/TLS certificate for HTTPS

### Features
- **Custom Domain**: crickounter.rajathverse.com
- **HTTPS Redirect**: All traffic redirected to secure HTTPS
- **Global CDN**: Fast loading times worldwide
- **HTTP/2 Support**: Modern protocol support
- **IPv6 Enabled**: Future-proof networking

### Deployment Resources
```yaml
# Key CloudFormation Resources:
- S3 Bucket: Static website hosting
- CloudFront Distribution: CDN with custom domain
- Route 53 Record: DNS alias to CloudFront
- SSL Certificate: ACM certificate for HTTPS
```

## 📱 Browser Compatibility

- **Modern Browsers**: Chrome, Firefox, Safari, Edge (latest versions)
- **Mobile Support**: iOS Safari, Chrome Mobile, Samsung Internet
- **Features Used**: 
  - CSS Grid & Flexbox
  - CSS Variables
  - Local Storage API
  - Fullscreen API
  - Web Audio API

## 🎨 Customization

### Themes
The application supports both dark and light themes with CSS variables:
```css
:root {
  --primary: #1e40af;
  --surface: #ffffff;
  --text-primary: #0f172a;
  /* ... more variables */
}

[data-theme="dark"] {
  --surface: #0f172a;
  --text-primary: #f1f5f9;
  /* ... dark theme overrides */
}
```

### Match Settings
- **Overs**: Configurable from 1-100 overs per innings
- **Players**: Adjustable team size (2-20 players)
- **Sound**: Toggle audio feedback on/off
- **Auto-save**: Automatic game state persistence

## 🔧 Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/rajathverse/crickounter.git
   cd crickounter
   ```

2. **Open in browser**:
   Simply open `scorecard.html` in your preferred web browser

3. **Local server** (optional):
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   ```

## 🚀 Deployment

### Manual Deployment
1. Upload `scorecard.html` to your web server
2. Ensure the server serves HTML files correctly
3. Configure HTTPS if needed

### AWS Deployment
1. **Deploy Infrastructure**:
   ```bash
   aws cloudformation deploy \
     --template-file crickounter-site.yml \
     --stack-name crickounter-site \
     --parameter-overrides \
       SubDomainName=crickounter.yourdomain.com \
       HostedZoneName=yourdomain.com. \
       BucketName=your-bucket-name
   ```

2. **Upload Content**:
   ```bash
   aws s3 sync . s3://your-bucket-name --exclude "*.yml" --exclude "README.md"
   ```

3. **Invalidate CDN**:
   ```bash
   aws cloudfront create-invalidation \
     --distribution-id YOUR_DISTRIBUTION_ID \
     --paths "/*"
   ```

## 📊 Performance Features

- **Optimized Loading**: Preloaded fonts and minimal dependencies
- **Efficient Rendering**: CSS transforms and GPU acceleration
- **Memory Management**: Efficient state management and cleanup
- **Responsive Design**: Mobile-first approach with optimized layouts

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Rajath Chowdhury**
- Website: [rajathverse.com](https://rajathverse.com)
- GitHub: [@rjrajath](https://github.com/rjrajath)
- Twitter: [@rjrajathm47](https://twitter.com/rjrajathm47)

## 🙏 Acknowledgments

- **Font Awesome** for the beautiful icons
- **Google Fonts** for Inter and JetBrains Mono fonts
- **Canvas Confetti** for celebration animations
- **HTML2Canvas** for screenshot functionality
- **AWS** for reliable cloud infrastructure

---

Made with ❤️ for cricket enthusiasts worldwide! 🏏

*Passionately crafted by [rajathverse.com](https://rajathverse.com)*
