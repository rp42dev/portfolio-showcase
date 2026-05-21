# 🌌 Premium Portfolio Showcase Hosting

This repository hosts your high-fidelity, self-contained **Plugins, Websites & Custom Apps** portfolio showcase. It is optimized for zero-overhead background rendering and instant loading, making it perfect for direct iframe embedding on your main WordPress site.

---

## 🚀 Live Hosting via GitHub Pages

To make this portfolio accessible under your public domain or a `github.io` URL, enable GitHub Pages:

1. Go to your repository settings on GitHub: **`https://github.com/rp42dev/portfolio-showcase/settings`**
2. In the left-hand sidebar, click on **Pages**.
3. Under **Build and deployment** -> **Source**, select **Deploy from a branch**.
4. Under **Branch**, select **`main`** and **`/ (root)`**, then click **Save**.
5. After 1–2 minutes, GitHub will publish your page and provide a public URL like:
   `https://rp42dev.github.io/portfolio-showcase/`

---

## 🔌 How to Embed on Your WordPress Website

Once GitHub Pages is enabled, you can embed the entire interactive portfolio seamlessly on your WordPress site (e.g., in a **Custom HTML** Gutenberg block, Elementor HTML widget, or theme template).

### 1. Seamless iframe Embed Code (Recommended)
```html
<iframe 
  src="https://rp42dev.github.io/portfolio-showcase/" 
  style="width: 100%; border: none; background: transparent; transition: height 0.3s ease;" 
  id="portfolio-iframe"
  scrolling="no">
</iframe>

<script>
  // Automatically adjust height to content if needed, or set a solid viewport height
  const iframe = document.getElementById('portfolio-iframe');
  
  // Set a robust default height that fits the grid beautifully
  iframe.style.height = '1450px'; 
  
  // Responsive height adjustment based on screen size
  function adjustIframeHeight() {
    if (window.innerWidth < 768) {
      // Mobile layout (single-column cards)
      iframe.style.height = '3100px';
    } else if (window.innerWidth < 1024) {
      // Tablet layout (2-column cards)
      iframe.style.height = '1850px';
    } else {
      // Desktop layout (3-column cards)
      iframe.style.height = '1450px';
    }
  }
  
  window.addEventListener('resize', adjustIframeHeight);
  adjustIframeHeight();
</script>
```

### 2. Native Inline HTML Snippet
If you prefer not to use an iframe and want the page to load natively within the WordPress page DOM (inheriting your theme's global script triggers):
* Copy the full content of `wp-portfolio-snippet.html` and paste it directly into a **Custom HTML** block on your WordPress site.

---

## 🎨 Files Included
* **`index.html`**: The full, self-contained showcase page containing all layouts, custom SVGs, high-end styling, and dynamic modal interaction controllers. (Renamed from `portfolio.html` to serve automatically as the home page on GitHub Pages).
* **`wp-portfolio-snippet.html`**: A modular, stripped snippet (outer container paddings set to 0, HTML footer stripped) designed specifically for native copy-pasting into WordPress custom widgets without double-footers or large gaps.
