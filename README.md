# Launch Site for WorkInPilot MVP

This is a standalone marketing/launch page for WorkInPilot MVP participants.

## Structure

```
launch-site/
├── index.html              # Single-page launch site
├── styles/
│   ├── modern-minimal.css  # Clean, minimal gray style
│   └── subtle-color.css    # Warm, conservative color style
├── assets/
│   ├── samples/            # Sample resume PDFs (12 total, 3 per domain)
│   │   ├── tech-sample-1.pdf
│   │   ├── tech-sample-2.pdf
│   │   ├── tech-sample-3.pdf
│   │   ├── marketing-sample-1.pdf
│   │   ├── marketing-sample-2.pdf
│   │   ├── marketing-sample-3.pdf
│   │   ├── sales-sample-1.pdf
│   │   ├── sales-sample-2.pdf
│   │   ├── sales-sample-3.pdf
│   │   ├── creatives-sample-1.pdf
│   │   ├── creatives-sample-2.pdf
│   │   └── creatives-sample-3.pdf
│   └── favicon.ico         # Optional favicon
└── README.md               # This file
```

## Deployment

### To deploy to `/var/www/html/launch.workinpilot.fun`:

1. **Copy files to server:**
   ```bash
   cd launch-site
   rsync -avz . user@your-server:/var/www/html/launch.workinpilot.fun/
   ```

2. **Set proper permissions:**
   ```bash
   ssh user@your-server
   cd /var/www/html/launch.workinpilot.fun
   chown -R www-data:www-data .
   chmod -R 755 .
   ```

3. **Optional: Set up Apache/Nginx:**
   ```apache
   # Apache example
   <VirtualHost *:80>
       ServerName launch.workinpilot.fun
       DocumentRoot /var/www/html/launch.workinpilot.fun
       
       <Directory /var/www/html/launch.workinpilot.fun>
           Options Indexes FollowSymLinks
           AllowOverride None
           Require all granted
       </Directory>
   </VirtualHost>
   ```

## Features

- **Single-page design** with 4 professional domains (tech, marketing, sales, creatives)
- **Get Started** bullet lists for each domain
- **Sample resume downloads** (3 per domain)
- **Style toggle** button to switch between two CSS themes
- **Launch button** linking to main app at https://app.workinpilot.net
- **Mobile responsive** design
- **Clean, conservative styling** (no flashy marketing aesthetics)

## Style Themes

1. **modern-minimal.css**: Clean, monochrome style with subtle gray tones
2. **subtle-color.css**: Warm, conservative style with gentle teal accents

## Adding Sample Resumes

Place your sample resume PDFs in `assets/samples/` with these exact filenames:
- `tech-sample-1.pdf`, `tech-sample-2.pdf`, `tech-sample-3.pdf`
- `marketing-sample-1.pdf`, `marketing-sample-2.pdf`, `marketing-sample-3.pdf`
- `sales-sample-1.pdf`, `sales-sample-2.pdf`, `sales-sample-3.pdf`
- `creatives-sample-1.pdf`, `creatives-sample-2.pdf`, `creatives-sample-3.pdf`

## Testing

1. Open `index.html` in a browser
2. Click the 🎨 toggle button to switch between styles
3. Test resume download links (will work once PDFs are added)
4. Click "Launch WorkInPilot" button to verify app link

## Notes

- No authentication required - public page
- Not included in sitemap/robots.txt
- Static HTML deployment
- Easy to update content by editing HTML
- Easy to experiment with styles by modifying CSS

