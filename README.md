const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

app.get('/api/status', (req, res) => {
  res.json({ status: '🔥 Server is running with swag!' });
});

app.post('/api/echo', (req, res) => {
  const { message } = req.body;
  if (!message) {
    return res.status(400).json({ error: 'No swag message provided!' });
  }
  res.json({ echoed: message });
});

app.listen(PORT, () => {
  console.log(`🚀 Swaggy backend server running on http://localhost:${PORT}`);
});
