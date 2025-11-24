# ADHD Self-Assessment Test (ASRS-v1.1)

A web-based implementation of the Adult ADHD Self-Report Scale (ASRS-v1.1) 6-question screening tool. This simple, scientifically validated test helps identify potential ADHD symptoms in adults.

🔗 **[Take the Test](https://yourusername.github.io/adhd-screening-test/)**

## About the Test

The ASRS-v1.1 is a World Health Organization (WHO) screening tool with:
- **69% sensitivity** - correctly identifies ~2/3 of adults with ADHD
- **99.5% specificity** - very rarely flags non-ADHD individuals
- **6 questions** - takes only 2-3 minutes to complete
- **87.5% positive predictive value** - if you score ≥4, there's a high likelihood of ADHD

## ⚠️ Important Disclaimer

**This is a screening tool, not a diagnosis.** Only qualified healthcare professionals can diagnose ADHD. If you score highly, consider discussing the results with your doctor or a mental health professional.

## Features

- ✅ Clean, accessible interface
- ✅ Mobile-responsive design
- ✅ Progress tracking
- ✅ Instant results with interpretation
- ✅ No data collection - completely private
- ✅ Works offline after initial load
- ✅ Print-friendly results

## Quick Deployment Guide

📖 **New to GitHub Pages?** See [DEPLOYMENT_GUIDE.md](DEPLOYMENT_GUIDE.md) for detailed step-by-step instructions.

### Option 1: Deploy Your Own Copy (Recommended)

1. **Fork this repository** by clicking the "Fork" button at the top right

2. **Enable GitHub Pages:**
   - Go to Settings → Pages
   - Source: Deploy from branch
   - Branch: main (or master)
   - Folder: / (root)
   - Click Save

3. **Access your test** at:
   ```
   https://[your-username].github.io/adhd-screening-test/
   ```

### Option 2: Download and Host

1. Download the `index.html` file
2. Upload to any web hosting service
3. No build process or dependencies required!

### Option 3: Run Locally

```bash
# Clone the repository
git clone https://github.com/yourusername/adhd-screening-test.git

# Navigate to the folder
cd adhd-screening-test

# Open in browser
open index.html
# or
python -m http.server 8000  # Then visit http://localhost:8000
```

## Technical Details

### Stack
- Pure HTML5, CSS3, and JavaScript (all in one file)
- No frameworks or dependencies
- Single-file application (`index.html`) for easy deployment
- SessionStorage for answer persistence
- No build process required

### Browser Support
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS 14+, Android Chrome)

### Accessibility
- WCAG 2.1 AA compliant
- Keyboard navigation
- Screen reader support
- High contrast mode compatible
- Focus indicators

### Performance
- < 50KB total size
- Single HTTP request
- No external dependencies
- Loads instantly

## Scoring Algorithm

The test evaluates 6 questions with different thresholds:

**Questions 1-3:** Positive if answered "Sometimes", "Often", or "Very Often"  
**Questions 4-6:** Positive if answered "Often" or "Very Often"

**Result:** 4 or more positive responses suggest potential ADHD

## Development

### Customization

Edit the `index.html` file to customize:
- Colors: Update CSS variables in `:root`
- Text: Modify content directly in HTML
- Scoring: Adjust thresholds in the `questions` array

### Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Testing Checklist

- [ ] All 6 questions display correctly
- [ ] Scoring matches ASRS-v1.1 specification
- [ ] Navigation works (forward/back)
- [ ] Results are accurate
- [ ] Mobile responsive
- [ ] Accessibility features work
- [ ] Print layout is clean

## Resources

### About ADHD
- [CHADD - National Resource on ADHD](https://chadd.org/)
- [NIMH - Attention-Deficit/Hyperactivity Disorder](https://www.nimh.nih.gov/health/topics/attention-deficit-hyperactivity-disorder-adhd)
- [CDC - ADHD Information](https://www.cdc.gov/ncbddd/adhd/)

### Professional Help
- Consult your primary care physician
- Find ADHD specialists through your insurance provider
- Contact local mental health clinics
- University counseling centers (for students)

### About ASRS-v1.1
- [Official WHO ASRS Documentation](https://www.hcp.med.harvard.edu/ncs/asrs.php)
- [Validation Study](https://pubmed.ncbi.nlm.nih.gov/15841682/)

## License

This project is released under the MIT License. The ASRS-v1.1 screening tool is in the public domain.

## Credits

- ASRS-v1.1 developed by the World Health Organization (WHO)
- Validation: Kessler et al. (2005)
- Web implementation: [Your Name]

## Privacy

This tool:
- ✅ Runs entirely in your browser
- ✅ Stores no personal data
- ✅ Sends no data to servers
- ✅ Uses no cookies
- ✅ Has no analytics
- ✅ Temporary storage (sessionStorage) cleared on tab close

## Support

If you find this tool helpful, consider:
- ⭐ Starring this repository
- 🔗 Sharing with others who might benefit
- 💬 Providing feedback via Issues
- 🤝 Contributing improvements

---

**Remember:** Getting help for ADHD can be life-changing. If you suspect you have ADHD, please reach out to a healthcare professional. Treatment is available and effective for 70-90% of people with ADHD.
