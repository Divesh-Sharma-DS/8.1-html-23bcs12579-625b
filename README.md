# 8.1-html-23bcs12579-625b
Create login form with React state management.


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>React Login Form</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <style>
      body {
        background-color: #0f172a;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }

      .login-container {
        background-color: #1e293b;
        padding: 40px;
        border-radius: 12px;
        box-shadow: 0px 0px 15px rgba(255, 255, 255, 0.1);
        width: 350px;
        text-align: center;
      }

      h2 {
        margin-bottom: 20px;
      }

      input {
        width: 100%;
        padding: 10px;
        margin: 10px 0;
        border: none;
        border-radius: 8px;
      }

      button {
        width: 100%;
        padding: 10px;
        background-color: #3b82f6;
        color: white;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        font-size: 16px;
        transition: background 0.3s;
      }

      button:hover {
        background-color: #2563eb;
      }

      .message {
        margin-top: 15px;
        color: #22c55e;
      }
    </style>
  </head>

  <body>
    <div id="root"></div>

    <script type="text/babel">
      function LoginForm() {
        const [username, setUsername] = React.useState("");
        const [password, setPassword] = React.useState("");
        const [message, setMessage] = React.useState("");

        const handleSubmit = (e) => {
          e.preventDefault();
          if (username === "" || password === "") {
            setMessage("❌ Please enter all fields");
          } else {
            setMessage(`✅ Welcome, ${username}!`);
          }
        };

        return (
          <div className="login-container">
            <h2>🔐 Login</h2>
            <form onSubmit={handleSubmit}>
              <input
                type="text"
                placeholder="Username"
                value={username}
                onChange={(e) => setUsername(e.target.value)}
              />
              <input
                type="password"
                placeholder="Password"
                value={password}
                onChange={(e) => setPassword(e.target.value)}
              />
              <button type="submit">Login</button>
            </form>
            {message && <p className="message">{message}</p>}
          </div>
        );
      }

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<LoginForm />);
    </script>
  </body>
</html>
