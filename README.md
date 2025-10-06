<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/EmulatorJS/EmulatorJS@main/docs/Logo-light.png" width="275"/><br>
  
  #
  
  **https://github.com/EmulatorJS/EmulatorJS**
  
</div>

> [!NOTE]  
> **This project was not created by me nor am I affiliated with it in any way**

<div align="center">
  
  ## Example HTML For The Demo:
  
</div>

```html
<!doctype html>
<html>

<body>
    <script>
        ejs();
        function ejs() {
            try {
                fetch("https://cdn.jsdelivr.net/gh/joethun/EmulatorJS-With-Cores@main/EmulatorJS.html")
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
