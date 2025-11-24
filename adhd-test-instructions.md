# ADHD Self-Assessment Test - Development Instructions

## Project Overview
Build a single-page web application that implements the Adult ADHD Self-Report Scale (ASRS-v1.1) 6-question screening test. The application should be deployable on GitHub Pages and provide an accessible, user-friendly interface for self-assessment.

## Core Requirements

### 1. Test Implementation
- Display 6 questions from the ASRS-v1.1 screening tool
- Each question has 5 response options: Never, Rarely, Sometimes, Often, Very Often
- Score calculation: Questions answered "Sometimes", "Often", or "Very Often" for questions 1-3, and "Often" or "Very Often" for questions 4-6 count as positive responses
- Result threshold: 4 or more positive responses indicate potential ADHD

### 2. Questions to Include
```
1. How often do you have trouble wrapping up the final details of a project, once the challenging parts have been done?

2. How often do you have difficulty getting things in order when you have to do a task that requires organization?

3. How often do you have problems remembering appointments or obligations?

4. When you have a task that requires a lot of thought, how often do you avoid or delay getting started?

5. How often do you fidget or squirm with your hands or feet when you have to sit down for a long time?

6. How often do you feel overly active and compelled to do things, like you were driven by a motor?
```

### 3. User Interface Design

#### Layout Structure
- Clean, minimalist design with good accessibility
- Mobile-responsive layout
- Progress indicator showing current question (e.g., "Question 3 of 6")
- Clear, readable typography (minimum 16px font size)

#### Color Scheme
- Use calming, professional colors
- Primary: #2563eb (blue)
- Background: #f8fafc (light gray)
- Text: #1e293b (dark gray)
- Accent for scoring zones: 
  - Positive response areas: #fbbf24 (amber)
  - Negative response areas: #e2e8f0 (light gray)

#### Interactive Elements
- Radio buttons for answer selection
- Visual feedback when hovering over options
- "Next" button to proceed through questions (disabled until answer selected)
- "Previous" button to go back and change answers
- "Submit" button on final question

### 4. Results Page

#### Score Display
- Clear indication of score (X out of 6 positive responses)
- Visual representation (progress bar or pie chart)
- Interpretation of results based on threshold

#### Results Interpretation
If score >= 4:
```
"Your responses suggest you may benefit from a professional ADHD assessment. This screening tool has identified patterns consistent with ADHD symptoms. Consider discussing these results with a healthcare provider."
```

If score < 4:
```
"Your responses do not strongly indicate ADHD symptoms at this time. However, if you have concerns about attention or focus, consider discussing them with a healthcare provider."
```

#### Additional Information
Include disclaimer text:
```
Important: This is a screening tool, not a diagnosis. The ASRS-v1.1 has a sensitivity of 69% and specificity of 99.5%. Only a qualified healthcare professional can diagnose ADHD.
```

Include "Learn More" section with:
- Link to official ASRS documentation
- Brief explanation of ADHD
- Resources for finding professional help

### 5. Technical Implementation

#### File Structure
```
/
├── index.html
├── style.css
├── script.js
└── README.md
```

#### HTML Structure
- Semantic HTML5 elements
- ARIA labels for accessibility
- Meta tags for SEO and social sharing

#### CSS Requirements
- Flexbox or Grid for layout
- CSS animations for transitions
- Print-friendly styles
- Dark mode support (optional but recommended)

#### JavaScript Functionality
```javascript
// Core data structure
const questions = [
  {
    id: 1,
    text: "How often do you have trouble wrapping up...",
    scoringThreshold: 3 // "Sometimes" or higher
  },
  // ... other questions
];

// State management
let currentQuestion = 0;
let answers = {};

// Core functions needed:
// - renderQuestion(questionIndex)
// - saveAnswer(questionId, value)
// - calculateScore()
// - displayResults(score)
// - navigation (next, previous)
// - validateAnswer()
// - resetTest()
```

### 6. Features to Implement

#### Essential Features
1. Question navigation with validation
2. Answer persistence (store in sessionStorage)
3. Score calculation and display
4. Mobile-responsive design
5. Keyboard navigation support
6. "Start Over" button on results page
7. Shareable results URL (optional: using URL parameters)

#### Enhanced Features
1. Progress save/resume functionality
2. Email results to self (using mailto: link)
3. Print-friendly results page
4. Language toggle (start with English only)
5. Anonymous analytics (optional, with consent)
6. Smooth transitions between questions
7. Loading states and error handling

### 7. Accessibility Requirements
- WCAG 2.1 AA compliance
- Keyboard navigation (Tab, Enter, Arrow keys)
- Screen reader support
- High contrast mode support
- Focus indicators
- Alt text for any images
- Proper heading hierarchy

### 8. Performance Optimization
- Minimize CSS and JavaScript
- Optimize for Core Web Vitals
- Lazy loading for any images
- Cache static assets
- Total page size < 100KB

### 9. GitHub Pages Deployment

#### Repository Structure
```
Repository name: adhd-screening-test
Branch: main (or gh-pages)
```

#### Deployment Steps
1. Create public repository
2. Add all files to main branch
3. Enable GitHub Pages in Settings
4. Set source to main branch, root folder
5. Add custom domain (optional)

#### README.md Content
Include:
- Test description and purpose
- Link to live site
- Disclaimer about medical advice
- Credits to ASRS-v1.1
- License information
- Contributing guidelines

### 10. Testing Requirements

#### Browser Compatibility
- Chrome (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)
- Edge (latest 2 versions)
- Mobile browsers (iOS Safari, Chrome Mobile)

#### Test Scenarios
1. Complete test flow with all answer combinations
2. Navigation (forward and backward)
3. Edge cases (no answer selected, browser refresh)
4. Accessibility testing with screen readers
5. Mobile responsiveness at various breakpoints
6. Print functionality
7. Sharing functionality

### 11. Code Quality Standards
- Use ES6+ JavaScript
- Comment complex logic
- Follow consistent naming conventions
- No console errors or warnings
- Validate HTML and CSS
- ESLint for JavaScript (optional)

### 12. Privacy and Ethics
- No personal data collection
- Clear disclaimer about medical advice
- Links to professional resources
- Respectful, non-stigmatizing language
- Option to clear all data

## Example Implementation Snippet

```html
<!-- Question template -->
<div class="question-container">
  <div class="progress">Question <span id="current">1</span> of 6</div>
  <h2 class="question-text">How often do you have trouble wrapping up the final details of a project, once the challenging parts have been done?</h2>
  <div class="answer-options">
    <label class="option">
      <input type="radio" name="q1" value="1">
      <span>Never</span>
    </label>
    <!-- More options -->
  </div>
  <div class="navigation">
    <button id="prev" disabled>Previous</button>
    <button id="next" disabled>Next</button>
  </div>
</div>
```

## Deliverables
1. Complete source code (HTML, CSS, JavaScript)
2. README with setup instructions
3. Live demo on GitHub Pages
4. Screenshots for documentation
5. License file (MIT recommended)

## Success Criteria
- Test loads and functions correctly on GitHub Pages
- All 6 questions display properly
- Scoring algorithm matches ASRS-v1.1 specification
- Results are accurate and clearly presented
- Site is accessible and mobile-friendly
- Code is clean, commented, and maintainable
