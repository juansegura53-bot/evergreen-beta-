

<!DOCTYPE html>

<html lang="en">

<head>

&nbsp;   <meta charset="UTF-8">

&nbsp;   <meta name="viewport" content="width=device-width, initial-scale=1.0">

&nbsp;   <title>Evergreen AI Platform</title>

&nbsp;   <style>

&nbsp;       \* {

&nbsp;           margin: 0;

&nbsp;           padding: 0;

&nbsp;           box-sizing: border-box;

&nbsp;       }

&nbsp;       

&nbsp;       body {

&nbsp;           font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;

&nbsp;           background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #0f172a 100%);

&nbsp;           color: #e2e8f0;

&nbsp;           min-height: 100vh;

&nbsp;       }

&nbsp;       

&nbsp;       .container {

&nbsp;           display: flex;

&nbsp;           height: 100vh;

&nbsp;       }

&nbsp;       

&nbsp;       .sidebar {

&nbsp;           width: 250px;

&nbsp;           background: rgba(15, 23, 42, 0.8);

&nbsp;           border-right: 1px solid rgba(148, 163, 184, 0.1);

&nbsp;           padding: 20px;

&nbsp;           overflow-y: auto;

&nbsp;       }

&nbsp;       

&nbsp;       .sidebar h2 {

&nbsp;           color: #06b6d4;

&nbsp;           font-size: 14px;

&nbsp;           margin-bottom: 20px;

&nbsp;           text-transform: uppercase;

&nbsp;           letter-spacing: 1px;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-btn {

&nbsp;           width: 100%;

&nbsp;           padding: 12px;

&nbsp;           margin-bottom: 8px;

&nbsp;           background: transparent;

&nbsp;           border: 1px solid rgba(148, 163, 184, 0.2);

&nbsp;           color: #94a3b8;

&nbsp;           cursor: pointer;

&nbsp;           border-radius: 6px;

&nbsp;           text-align: left;

&nbsp;           font-size: 14px;

&nbsp;           transition: all 0.3s;

&nbsp;       }

&nbsp;       

&nbsp;       .nav-btn:hover {

&nbsp;           background: rgba(6, 182, 212, 0.1);

&nbsp;           color: #06b6d4;

&nbsp;           border-color: rgba(6, 182, 212, 0.3);

&nbsp;       }

&nbsp;       

&nbsp;       .nav-btn.active {

&nbsp;           background: rgba(6, 182, 212, 0.2);

&nbsp;           color: #06b6d4;

&nbsp;           border-color: rgba(6, 182, 212, 0.5);

&nbsp;       }

&nbsp;       

&nbsp;       .main {

&nbsp;           flex: 1;

&nbsp;           display: flex;

&nbsp;           flex-direction: column;

&nbsp;       }

&nbsp;       

&nbsp;       .header {

&nbsp;           background: rgba(30, 41, 59, 0.5);

&nbsp;           border-bottom: 1px solid rgba(148, 163, 184, 0.1);

&nbsp;           padding: 20px 30px;

&nbsp;           backdrop-filter: blur(10px);

&nbsp;       }

&nbsp;       

&nbsp;       .header h1 {

&nbsp;           color: #06b6d4;

&nbsp;           font-size: 28px;

&nbsp;           margin-bottom: 5px;

&nbsp;       }

&nbsp;       

&nbsp;       .header p {

&nbsp;           color: #94a3b8;

&nbsp;           font-size: 14px;

&nbsp;       }

&nbsp;       

&nbsp;       .content {

&nbsp;           flex: 1;

&nbsp;           overflow-y: auto;

&nbsp;           padding: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .section {

&nbsp;           display: none;

&nbsp;       }

&nbsp;       

&nbsp;       .section.active {

&nbsp;           display: block;

&nbsp;       }

&nbsp;       

&nbsp;       .metric-grid {

&nbsp;           display: grid;

&nbsp;           grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));

&nbsp;           gap: 20px;

&nbsp;           margin-bottom: 30px;

&nbsp;       }

&nbsp;       

&nbsp;       .metric-card {

&nbsp;           background: linear-gradient(135deg, rgba(6, 182, 212, 0.1), rgba(6, 182, 212, 0.05));

&nbsp;           border: 1px solid rgba(6, 182, 212, 0.2);

&nbsp;           border-radius: 8px;

&nbsp;           padding: 20px;

&nbsp;       }

&nbsp;       

&nbsp;       .metric-label {

&nbsp;           color: #94a3b8;

&nbsp;           font-size: 12px;

&nbsp;           text-transform: uppercase;

&nbsp;           margin-bottom: 8px;

&nbsp;       }

&nbsp;       

&nbsp;       .metric-value {

&nbsp;           color: #06b6d4;

&nbsp;           font-size: 32px;

&nbsp;           font-weight: bold;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group {

&nbsp;           margin-bottom: 15px;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group label {

&nbsp;           display: block;

&nbsp;           color: #e2e8f0;

&nbsp;           margin-bottom: 8px;

&nbsp;           font-size: 14px;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group input,

&nbsp;       .form-group select,

&nbsp;       .form-group textarea {

&nbsp;           width: 100%;

&nbsp;           padding: 10px;

&nbsp;           background: rgba(15, 23, 42, 0.8);

&nbsp;           border: 1px solid rgba(148, 163, 184, 0.2);

&nbsp;           color: #e2e8f0;

&nbsp;           border-radius: 6px;

&nbsp;           font-size: 14px;

&nbsp;       }

&nbsp;       

&nbsp;       .form-group textarea {

&nbsp;           resize: vertical;

&nbsp;           min-height: 100px;

&nbsp;       }

&nbsp;       

&nbsp;       .btn {

&nbsp;           padding: 12px 24px;

&nbsp;           background: #06b6d4;

&nbsp;           color: #0f172a;

&nbsp;           border: none;

&nbsp;           border-radius: 6px;

&nbsp;           cursor: pointer;

&nbsp;           font-weight: 600;

&nbsp;           transition: all 0.3s;

&nbsp;       }

&nbsp;       

&nbsp;       .btn:hover {

&nbsp;           background: #0891b2;

&nbsp;           transform: translateY(-2px);

&nbsp;       }

&nbsp;       

&nbsp;       .call-item {

&nbsp;           background: rgba(15, 23, 42, 0.5);

&nbsp;           border: 1px solid rgba(148, 163, 184, 0.2);

&nbsp;           border-radius: 6px;

&nbsp;           padding: 15px;

&nbsp;           margin-bottom: 15px;

&nbsp;       }

&nbsp;       

&nbsp;       .call-item h3 {

&nbsp;           color: #e2e8f0;

&nbsp;           margin-bottom: 8px;

&nbsp;       }

&nbsp;       

&nbsp;       .call-item p {

&nbsp;           color: #94a3b8;

&nbsp;           font-size: 13px;

&nbsp;           margin-bottom: 5px;

&nbsp;       }

&nbsp;       

&nbsp;       .status-badge {

&nbsp;           display: inline-block;

&nbsp;           padding: 4px 12px;

&nbsp;           border-radius: 4px;

&nbsp;           font-size: 12px;

&nbsp;           font-weight: 600;

&nbsp;           margin-top: 10px;

&nbsp;       }

&nbsp;       

&nbsp;       .status-new {

&nbsp;           background: rgba(59, 130, 246, 0.2);

&nbsp;           color: #3b82f6;

&nbsp;       }

&nbsp;       

&nbsp;       .status-quoted {

&nbsp;           background: rgba(234, 179, 8, 0.2);

&nbsp;           color: #eab308;

&nbsp;       }

&nbsp;       

&nbsp;       .status-scheduled {

&nbsp;           background: rgba(34, 197, 94, 0.2);

&nbsp;           color: #22c55e;

&nbsp;       }

&nbsp;       

&nbsp;       .quote-amount {

&nbsp;           color: #10b981;

&nbsp;           font-weight: bold;

&nbsp;           font-size: 18px;

&nbsp;           margin-top: 10px;

&nbsp;       }

&nbsp;       

&nbsp;       .box {

&nbsp;           background: rgba(30, 41, 59, 0.5);

&nbsp;           border: 1px solid rgba(148, 163, 184, 0.2);

&nbsp;           border-radius: 8px;

&nbsp;           padding: 20px;

&nbsp;           margin-bottom: 20px;

&nbsp;       }

&nbsp;   </style>

</head>

<body>

&nbsp;   <div class="container">

&nbsp;       <div class="sidebar">

&nbsp;           <h2>Evergreen</h2>

&nbsp;           <button class="nav-btn active" onclick="showTab('dashboard')">📊 Dashboard</button>

&nbsp;           <button class="nav-btn" onclick="showTab('calls')">📞 Call Simulator</button>

&nbsp;           <button class="nav-btn" onclick="showTab('quotes')">📄 Quotes</button>

&nbsp;           <button class="nav-btn" onclick="showTab('assistant')">💬 AI Assistant</button>

&nbsp;       </div>

&nbsp;       

&nbsp;       <div class="main">

&nbsp;           <div class="header">

&nbsp;               <h1>Evergreen Tree Service</h1>

&nbsp;               <p>AI Office Manager Beta Platform</p>

&nbsp;           </div>

&nbsp;           

&nbsp;           <div class="content">

&nbsp;               <div id="dashboard" class="section active">

&nbsp;                   <h2 style="margin-bottom: 20px; color: #06b6d4;">Dashboard</h2>

&nbsp;                   <div class="metric-grid">

&nbsp;                       <div class="metric-card">

&nbsp;                           <div class="metric-label">Today's Calls</div>

&nbsp;                           <div class="metric-value" id="totalCalls">3</div>

&nbsp;                       </div>

&nbsp;                       <div class="metric-card">

&nbsp;                           <div class="metric-label">Quoted</div>

&nbsp;                           <div class="metric-value" id="quotedCount">2</div>

&nbsp;                       </div>

&nbsp;                       <div class="metric-card">

&nbsp;                           <div class="metric-label">Scheduled</div>

&nbsp;                           <div class="metric-value" id="scheduledCount">1</div>

&nbsp;                       </div>

&nbsp;                       <div class="metric-card">

&nbsp;                           <div class="metric-label">Pipeline</div>

&nbsp;                           <div class="metric-value" id="pipelineValue">$3,500</div>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;                   

&nbsp;                   <div class="box">

&nbsp;                       <h3 style="color: #06b6d4; margin-bottom: 15px;">📞 Today's Calls</h3>

&nbsp;                       <div id="callsList"></div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               

&nbsp;               <div id="calls" class="section">

&nbsp;                   <h2 style="margin-bottom: 20px; color: #06b6d4;">Simulate Incoming Call</h2>

&nbsp;                   <div class="box">

&nbsp;                       <div class="form-group">

&nbsp;                           <label>Customer Name</label>

&nbsp;                           <input type="text" id="simName" placeholder="e.g., John Smith">

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label>Phone Number</label>

&nbsp;                           <input type="tel" id="simPhone" placeholder="e.g., (503) 555-0142">

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label>Address</label>

&nbsp;                           <input type="text" id="simAddress" placeholder="e.g., 1234 Oak St, Portland, OR">

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label>Service Type</label>

&nbsp;                           <select id="simService">

&nbsp;                               <option>Tree Removal</option>

&nbsp;                               <option>Tree Trimming</option>

&nbsp;                               <option>Stump Grinding</option>

&nbsp;                               <option>Emergency Tree Service</option>

&nbsp;                           </select>

&nbsp;                       </div>

&nbsp;                       <div class="form-group">

&nbsp;                           <label>What They Said</label>

&nbsp;                           <textarea id="simTranscript" placeholder="e.g., Large oak tree, needs removal"></textarea>

&nbsp;                       </div>

&nbsp;                       <button class="btn" onclick="simulateCall()">📞 Simulate Call Intake</button>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;               

&nbsp;               <div id="quotes" class="section">

&nbsp;                   <h2 style="margin-bottom: 20px; color: #06b6d4;">Generate Quotes</h2>

&nbsp;                   <div id="quotesList"></div>

&nbsp;               </div>

&nbsp;               

&nbsp;               <div id="assistant" class="section">

&nbsp;                   <h2 style="margin-bottom: 20px; color: #06b6d4;">AI Assistant</h2>

&nbsp;                   <div class="chat-container">

&nbsp;                       <div class="chat-messages" id="chatMessages">

&nbsp;                           <div class="chat-message bot">

&nbsp;                               <p>Hey! Ask me about calls, quotes, revenue, or appointments. What do you need?</p>

&nbsp;                           </div>

&nbsp;                       </div>

&nbsp;                       <div class="chat-input-group">

&nbsp;                           <input type="text" id="chatInput" placeholder="Ask anything..." onkeypress="if(event.key==='Enter') sendChat()">

&nbsp;                           <button class="btn" onclick="sendChat()">Send</button>

&nbsp;                       </div>

&nbsp;                   </div>

&nbsp;               </div>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </div>



&nbsp;   <script>

&nbsp;       let calls = \[

&nbsp;           { id: 1, name: 'John Smith', phone: '(503) 555-0142', address: '1234 Oak St, Portland, OR', service: 'Tree Removal', transcript: 'Large oak tree, 60 feet, close to house', status: 'new', quote: null },

&nbsp;           { id: 2, name: 'Sarah Johnson', phone: '(503) 555-0198', address: '5678 Pine Ave, Hillsboro, OR', service: 'Stump Grinding', transcript: '5 stumps need grinding', status: 'quoted', quote: 1500 },

&nbsp;           { id: 3, name: 'Mike Davis', phone: '(503) 555-0156', address: '9012 Elm Rd, Beaverton, OR', service: 'Tree Trimming', transcript: 'Branches dropping on neighbor garage', status: 'scheduled', quote: 800 }

&nbsp;       ];

&nbsp;       

&nbsp;       let chatMessages = \['Hey! Ask me about calls, quotes, revenue, or appointments. What do you need?'];

&nbsp;       

&nbsp;       const pricing = {

&nbsp;           'Tree Removal': 1200,

&nbsp;           'Tree Trimming': 650,

&nbsp;           'Stump Grinding': 350,

&nbsp;           'Emergency Tree Service': 2500

&nbsp;       };

&nbsp;       

&nbsp;       function showTab(tab) {

&nbsp;           document.querySelectorAll('.section').forEach(el => el.classList.remove('active'));

&nbsp;           document.getElementById(tab).classList.add('active');

&nbsp;           document.querySelectorAll('.nav-btn').forEach(el => el.classList.remove('active'));

&nbsp;           event.target.classList.add('active');

&nbsp;           if (tab === 'dashboard') updateDashboard();

&nbsp;           else if (tab === 'quotes') updateQuotes();

&nbsp;       }

&nbsp;       

&nbsp;       function updateDashboard() {

&nbsp;           document.getElementById('totalCalls').textContent = calls.length;

&nbsp;           document.getElementById('quotedCount').textContent = calls.filter(c => c.quote).length;

&nbsp;           document.getElementById('scheduledCount').textContent = calls.filter(c => c.status === 'scheduled').length;

&nbsp;           const total = calls.filter(c => c.quote).reduce((sum, c) => sum + c.quote, 0);

&nbsp;           document.getElementById('pipelineValue').textContent = '$' + total.toLocaleString();

&nbsp;           const callsList = document.getElementById('callsList');

&nbsp;           callsList.innerHTML = calls.map(call => `<div class="call-item"><h3>${call.name}</h3><p><strong>${call.service}</strong></p><p>${call.address}</p>${call.quote ? `<p class="quote-amount">$${call.quote}</p>` : ''}<span class="status-badge status-${call.status}">${call.status.toUpperCase()}</span></div>`).join('');

&nbsp;       }

&nbsp;       

&nbsp;       function simulateCall() {

&nbsp;           const name = document.getElementById('simName').value;

&nbsp;           const phone = document.getElementById('simPhone').value;

&nbsp;           const address = document.getElementById('simAddress').value;

&nbsp;           const service = document.getElementById('simService').value;

&nbsp;           const transcript = document.getElementById('simTranscript').value;

&nbsp;           if (!name || !phone) { alert('Please fill in name and phone'); return; }

&nbsp;           const newCall = { id: calls.length + 1, name, phone, address, service, transcript, status: 'new', quote: null };

&nbsp;           calls.unshift(newCall);

&nbsp;           document.getElementById('simName').value = '';

&nbsp;           document.getElementById('simPhone').value = '';

&nbsp;           document.getElementById('simAddress').value = '';

&nbsp;           document.getElementById('simTranscript').value = '';

&nbsp;           alert('✓ Call captured! Go to Dashboard to see it.');

&nbsp;       }

&nbsp;       

&nbsp;       function updateQuotes() {

&nbsp;           const newCalls = calls.filter(c => c.status === 'new');

&nbsp;           const quotesList = document.getElementById('quotesList');

&nbsp;           if (newCalls.length === 0) { quotesList.innerHTML = '<p style="text-align: center; color: #94a3b8;">No new leads. Simulate a call first!</p>'; return; }

&nbsp;           quotesList.innerHTML = newCalls.map(call => {

&nbsp;               const price = pricing\[call.service] || 1000;

&nbsp;               return `<div class="box"><h3>${call.name}</h3><p>${call.service}</p><p style="color: #94a3b8; margin: 10px 0;">"${call.transcript}"</p><div style="background: rgba(16, 185, 129, 0.1); padding: 15px; border-radius: 6px; margin: 15px 0;"><p style="color: #94a3b8; font-size: 12px;">ESTIMATED QUOTE</p><p style="color: #10b981; font-size: 32px; font-weight: bold;">$${price}</p></div><button class="btn" onclick="generateQuote(${call.id}, ${price})">Generate \& Send Quote</button></div>`;

&nbsp;           }).join('');

&nbsp;       }

&nbsp;       

&nbsp;       function generateQuote(callId, price) {

&nbsp;           const call = calls.find(c => c.id === callId);

&nbsp;           if (call) { call.status = 'quoted'; call.quote = price; updateQuotes(); alert('✓ Quote generated and sent!'); }

&nbsp;       }

&nbsp;       

&nbsp;       function sendChat() {

&nbsp;           const input = document.getElementById('chatInput').value.trim();

&nbsp;           if (!input) return;

&nbsp;           chatMessages.push(input);

&nbsp;           let response = '';

&nbsp;           const lower = input.toLowerCase();

&nbsp;           if (lower.includes('how many') \&\& lower.includes('call')) response = `You have ${calls.length} calls today.`;

&nbsp;           else if (lower.includes('revenue') || lower.includes('money')) {

&nbsp;               const total = calls.filter(c => c.quote).reduce((sum, c) => sum + c.quote, 0);

&nbsp;               response = `Total quoted: $${total}. If all close, that's $${total} revenue.`;

&nbsp;           } else if (lower.includes('schedule') || lower.includes('appointment')) {

&nbsp;               const scheduled = calls.filter(c => c.status === 'scheduled');

&nbsp;               response = scheduled.length > 0 ? `You have ${scheduled.length} appointment(s) scheduled.` : 'No appointments yet.';

&nbsp;           } else if (lower.includes('close rate')) {

&nbsp;               const rate = calls.length > 0 ? Math.round(100 \* calls.filter(c => c.status === 'scheduled').length / calls.length) : 0;

&nbsp;               response = `Your close rate: ${rate}%. Goal: 55%.`;

&nbsp;           } else {

&nbsp;               response = 'I can help with: calls, revenue, appointments, close rate. What do you need?';

&nbsp;           }

&nbsp;           chatMessages.push(response);

&nbsp;           const chatDiv = document.getElementById('chatMessages');

&nbsp;           chatDiv.innerHTML = chatMessages.map((msg, i) => `<div class="chat-message ${i % 2 === 0 ? 'bot' : 'user'}"><p>${msg}</p></div>`).join('');

&nbsp;           chatDiv.scrollTop = chatDiv.scrollHeight;

&nbsp;           document.getElementById('chatInput').value = '';

&nbsp;       }

&nbsp;       

&nbsp;       updateDashboard();

&nbsp;   </script>

</body>

</html>

