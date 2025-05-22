<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link rel="stylesheet" href="home.css" />
  <title>중간과제 포트폴리오</title>
</head>
<body>
  <div class="top-bar-background"></div>

  <div class="circles absolute-circles">
    <div class="circle red"></div>
    <div class="circle yellow"></div>
    <div class="circle green"></div>
  </div>

  <nav class="nav absolute-nav font-departure">
    <a href="home.html">home</a>
    <a href="works.html">works</a>
    <a href="about.html">about</a>
  </nav>

  <div class="content">
    <h1 id="typing-text" class="font-departure spaced-lines"></h1>
  </div>

  <footer>contact · kx.oir0@gmail.com<br>&copy; 2025 Sungmin Lim</footer>

  <script>
    const text = "Hello!\nwelcome to my\nPortfolio";
    const typingElement = document.getElementById("typing-text");
    let index = 0;
    let typingStarted = false;
  
    function type() {
      if (index < text.length) {
        const currentText = text.substring(0, index + 1).replace(/\n/g, "<br>");
        typingElement.innerHTML = currentText;
        index++;
        setTimeout(type, 40);
      } else {
        typingElement.innerHTML += '<span class="cursor"></span>';
      }
    }
  
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting && !typingStarted) {
          typingStarted = true;
          type();
          observer.unobserve(typingElement);
        }
      });
    }, {
      threshold: 0.6
    });
  
    observer.observe(typingElement);
  </script>
  
</body>
</html>
