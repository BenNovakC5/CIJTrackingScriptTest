<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CI-Journeys Web Tracking Test</title>

  <!-- Microsoft CI-Journeys tracking script -->
  <script>
    (function (a, t, i) {
      var e = "MSCI";
      var s = "Analytics";
      var o = e + "queue";
      a[o] = a[o] || [];
      var r = a[e] || function (n) {
        var t = {};
        t[s] = {};
        function e(e) {
          while (e.length) {
            var r = e.pop();
            t[s][r] = function (e) {
              return function () {
                a[o].push([e, n, arguments])
              }
            }(r)
          }
        }
        var r = "track";
        var i = "set";
        e([r + "Event", r + "View", r + "Action", i + "Config", i + "Property", i + "User", "initialize", "teardown"]);
        return t
      }(i.name);
      var n = i.name;
      if (!a[e]) {
        a[n] = r[s];
        a[o].push(["new", n]);
        setTimeout(function () {
          var e = "script";
          var r = t.createElement(e);
          r.async = 1;
          r.src = i.src;
          var n = t.getElementsByTagName(e)[0];
          n.parentNode.insertBefore(r, n)
        }, 1)
      } else {
        a[n] = new r[s]
      }
      if (i.user) {
        a[n].setUser(i.user)
      }
      if (i.props) {
        for (var c in i.props) {
          a[n].setProperty(c, i.props[c])
        }
      }
      a[n].initialize(i.cfg)
    })(window, document, {
      src: "https://cxppusa1rdrect01sa02cdn-endpoint.azureedge.net/webtracking/WebTracking/WebTracking.bundle.js",
      name: "MSCI",
      cfg: {
        ingestionKey: "52f0ba17c7844d429fc086d0de6fb659-85a2156c-84f9-4edf-b1cf-d49af41d84d9-7781",
        endpointUrl: "https://mobile.events.data.microsoft.com/OneCollector/1.0/",
        autoCapture: {
          view: true,
          click: true
        },
        orgInfo: {
          orgId: "e88400e7-cd52-ee11-94d2-002248282e24",
          orgTenantId: "ea528749-3090-4cf3-ae87-55557950ed63",
          orgGeo: "USA"
        }
      }
    });
  </script>

  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    nav a { margin: 0 10px; text-decoration: none; color: blue; }
    section { margin-top: 40px; }
    button { padding: 8px 16px; margin-top: 10px; }
  </style>
</head>
<body>
  <header>
    <h1>Customer Insights Web Tracking Demo</h1>
    <nav>
      <a href="#home" onclick="console.log('Visited Home')">Home</a>
      <a href="#features" onclick="console.log('Visited Features')">Features</a>
      <a href="#contact" onclick="console.log('Visited Contact')">Contact</a>
    </nav>
  </header>

  <section id="home">
    <h2>Home</h2>
    <p>Click the links or buttons to generate interactions for testing.</p>
    <button onclick="alert('CTA clicked!'); console.log('CTA clicked');">Click Me (CTA)</button>
  </section>

  <section id="features">
    <h2>Features</h2>
    <ul>
      <li onclick="console.log('Clicked Feature A')">Feature A</li>
      <li onclick="console.log('Clicked Feature B')">Feature B</li>
      <li onclick="console.log('Clicked Feature C')">Feature C</li>
    </ul>
    <button onclick="console.log('Requested Demo')">Request a Demo</button>
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <form onsubmit="console.log('Form Submitted'); alert('Form submitted!'); return false;">
      <label for="name">Name:</label><br>
      <input type="text" id="name" name="name" required /><br><br>
      <label for="email">Email:</label><br>
      <input type="email" id="email" name="email" required /><br><br>
      <button type="submit">Submit</button>
    </form>
  </section>

  <footer>
    <p>&copy; 2025 Web Tracking Test</p>
  </footer>
</body>
</html>
