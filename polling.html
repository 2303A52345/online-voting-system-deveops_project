const express = require("express");
const bodyParser = require("body-parser");
const app = express();
const PORT = 3000;

app.use(bodyParser.urlencoded({ extended: true }));

let users = []; // {username,password,phone,address,voted}
let currentUser = null;

const positions = {
  President: ["Meghana", "vaishnavi", "varsha"],
  "Vice President": ["rishitha", "veda", "rachana"],
  Secretary: ["srija", "mahi", "Pooja "],
  Treasurer: ["Priya ", "Navya", "Fatima"]
};

let votes = {};
for (let pos in positions) {
  votes[pos] = {};
  positions[pos].forEach(c => (votes[pos][c] = 0));
}

app.get("/", (req, res) => {
  res.send(page(`
    <h1>Online Polling System</h1>
    <a href="/register">Register</a>
    <a href="/login">Login</a>
  `));
});

app.get("/register", (req, res) => {
  res.send(page(`
    <h2>Register</h2>
    <form method="POST">
      <input name="username" placeholder="Username" required>
      <input name="password" type="password" placeholder="Password" required>
      <input name="phone" placeholder="Contact Number" required>
      <input name="address" placeholder="Address" required>
      <button>Register</button>
    </form>
  `));
});

app.post("/register", (req, res) => {
  users.push({ ...req.body, voted: false });
  res.redirect("/login");
});


app.get("/login", (req, res) => {
  res.send(page(`
    <h2>Login</h2>
    <form method="POST">
      <input name="username" placeholder="Username" required>
      <input name="password" type="password" placeholder="Password" required>
      <button>Login</button>
    </form>
  `));
});

app.post("/login", (req, res) => {
  const user = users.find(
    u => u.username === req.body.username && u.password === req.body.password
  );
  if (!user) return res.send(page("<h3> Invalid Login</h3><a href='/login'>Try Again</a>"));
  currentUser = user;
  res.redirect("/vote");
});

app.get("/vote", (req, res) => {
  if (!currentUser) return res.redirect("/login");
  if (currentUser.voted)
    return res.send(page("<h2>You already voted</h2><a href='/stats'>View Stats</a>"));

  let html = `<h2>Cast Your Vote</h2><form method="POST">`;

  for (let pos in positions) {
    html += `<h3>${pos}</h3>`;
    positions[pos].forEach(c => {
      html += `
        <label>
          <input type="radio" name="${pos}" value="${c}" required> ${c}
        </label>`;
    });
    html += `<hr>`;
  }

  html += `<button>Submit Vote</button></form>`;
  res.send(page(html));
});

app.post("/vote", (req, res) => {
  for (let pos in positions) {
    votes[pos][req.body[pos]]++;
  }
  currentUser.voted = true;
  res.redirect("/stats");
});

app.get("/stats", (req, res) => {
  const total = users.length;
  const voted = users.filter(u => u.voted).length;
  const notVoted = total - voted;

  let html = `
    <h2> Polling Statistics</h2>
    <p>Total Registered: <b>${total}</b></p>
    <p>People Voted: <b>${voted}</b></p>
    <p>People Not Voted: <b>${notVoted}</b></p>
    <hr>
  `;

  for (let pos in votes) {
    const totalVotes = Object.values(votes[pos]).reduce((a, b) => a + b, 0);
    html += `<h3>${pos}</h3>`;
    for (let c in votes[pos]) {
      const pct = totalVotes ? ((votes[pos][c] / totalVotes) * 100).toFixed(2) : 0;
      html += `<p>${c}: ${votes[pos][c]} (${pct}%)</p>`;
    }
    html += `<hr>`;
  }

  res.send(page(html + `<a href="/">Home</a>`));
});

function page(content) {
  return `
<!DOCTYPE html>
<html>
<head>
<title>Polling System</title>
<style>
body{
  margin:0;height:100vh;display:flex;justify-content:center;align-items:center;
  font-family:Segoe UI;background:linear-gradient(135deg,#667eea,#764ba2);color:white;
}
.card{
  width:420px;max-height:90vh;overflow:auto;
  background:rgba(255,255,255,0.15);
  backdrop-filter:blur(12px);padding:30px;border-radius:20px;
}
input{margin:6px}
button,a{
  margin:10px;padding:10px 22px;border-radius:22px;
  background:#ffdd57;color:black;font-weight:bold;border:none;text-decoration:none;
}
hr{border:1px solid rgba(255,255,255,0.3)}
</style>
</head>
<body>
<div class="card">${content}</div>
</body>
</html>`;
}

app.listen(PORT, () =>
  console.log("Server running → http://localhost:" + PORT)
);
