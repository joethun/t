<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/EmulatorJS/EmulatorJS@main/docs/Logo-light.png" width="275"/><br>
  
  #
  
  Example HTML For The Demo:
  
</div>

```html
<!doctype html>
<html>
<body>
    <script>
        ejs();
        function ejs() {
            try {
                fetch("https://cdn.jsdelivr.net/gh/joethun/EmulatorJS-With-Cores@main/index.html?t=" + Date.now())
                    .then(response => response.text())
                    .then(html => {
                        document.documentElement.innerHTML = html;
                        document.documentElement.querySelectorAll('script').forEach(oldScript => {
                            const newScript = document.createElement('script');
                            if (oldScript.src) {
                                newScript.src = oldScript.src;
                            } else {
                                newScript.textContent = oldScript.textContent;
                            }
                            document.body.appendChild(newScript);
                        });
                    });
            } catch (error) {
                console.error('error:', error);
            }
        }
    </script>
</body>
</html>
```
