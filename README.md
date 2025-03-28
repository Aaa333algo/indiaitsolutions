<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>India IT Solutions - Algo Trading</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #f5f5f5;
            position: relative;
            overflow-x: hidden;
        }

        /* Watermark */
        .watermark {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            pointer-events: none;
            z-index: -1;
            opacity: 0.05;
        }

        .watermark-text {
            font-size: 20vw;
            font-weight: 800;
            color: #1A237E;
            transform: rotate(-30deg);
            white-space: nowrap;
            user-select: none;
        }

        /* Login Page */
        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #1A237E 0%, #0d47a1 100%);
            position: relative;
        }

        .login-box {
            background: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            width: 400px;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #1A237E;
            margin-bottom: 20px;
        }

        .login-box h2 {
            margin-bottom: 30px;
            color: #333;
        }

        .input-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .input-group label {
            display: block;
            margin-bottom: 8px;
            color: #555;
        }

        .input-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }

        .login-btn {
            width: 100%;
            padding: 12px;
            background: linear-gradient(to right, #FF6D00, #FF9100);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .login-btn:hover {
            background: linear-gradient(to right, #FF9100, #FF6D00);
        }

        .forgot-password {
            margin-top: 15px;
            color: #777;
            font-size: 14px;
            cursor: pointer;
        }

        /* Dashboard */
        .dashboard {
            display: none;
            background-color: #f5f5f5;
            min-height: 100vh;
            position: relative;
        }

        .header {
            background: linear-gradient(135deg, #1A237E 0%, #0d47a1 100%);
            color: white;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
            z-index: 1;
        }

        .broker-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .broker-status {
            display: flex;
            align-items: center;
            background: rgba(255, 255, 255, 0.1);
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
        }

        .broker-status .status-dot {
            width: 10px;
            height: 10px;
            background-color: #4CAF50;
            border-radius: 50%;
            margin-right: 8px;
        }

        .algo-toggle {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .algo-toggle span {
            font-size: 14px;
        }

        .user-profile {
            display: flex;
            align-items: center;
            position: relative;
        }

        .profile-avatar {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background-color: #1A237E;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            margin-left: 15px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .profile-avatar:hover {
            transform: scale(1.1);
        }

        /* Profile Dropdown */
        .profile-dropdown {
            position: absolute;
            top: 50px;
            right: 0;
            background: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 250px;
            padding: 15px;
            z-index: 100;
            display: none;
        }

        .profile-dropdown.active {
            display: block;
        }

        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }

        .user-info-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: #1A237E;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            margin-right: 10px;
        }

        .user-details h4 {
            color: #333;
            font-size: 16px;
            margin-bottom: 3px;
        }

        .user-details p {
            color: #777;
            font-size: 12px;
        }

        .subscription-status {
            background: #FFF8E1;
            border-left: 3px solid #FFC107;
            padding: 10px;
            border-radius: 4px;
            margin-bottom: 15px;
        }

        .subscription-status h5 {
            color: #FF6D00;
            font-size: 14px;
            margin-bottom: 5px;
        }

        .subscription-status p {
            color: #555;
            font-size: 12px;
        }

        .profile-menu {
            list-style: none;
        }

        .profile-menu li {
            padding: 8px 0;
            border-bottom: 1px solid #f5f5f5;
        }

        .profile-menu li:last-child {
            border-bottom: none;
        }

        .profile-menu a {
            color: #555;
            text-decoration: none;
            font-size: 14px;
            display: flex;
            align-items: center;
        }

        .profile-menu a i {
            margin-right: 10px;
            color: #1A237E;
        }

        .profile-menu a:hover {
            color: #1A237E;
        }

        /* Scripts Control Section */
        .scripts-control {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            position: relative;
            z-index: 1;
        }

        .scripts-control h3 {
            color: #1A237E;
            margin-bottom: 20px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }

        .script-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }

        .script-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 15px;
            background: #f9f9f9;
            border-radius: 8px;
        }

        .script-name {
            font-weight: 500;
        }

        .script-controls {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .quantity-input {
            width: 60px;
            padding: 5px;
            border: 1px solid #ddd;
            border-radius: 4px;
            text-align: center;
        }

        /* Toggle Switch */
        .switch {
            position: relative;
            display: inline-block;
            width: 50px;
            height: 24px;
        }

        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider {
            background-color: #4CAF50;
        }

        input:checked + .slider:before {
            transform: translateX(26px);
        }

        /* Options Grid */
        .options-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .option-card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            cursor: pointer;
            transition: all 0.3s;
        }

        .option-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .option-card i {
            font-size: 40px;
            color: #1A237E;
            margin-bottom: 15px;
        }

        .option-card h3 {
            color: #333;
            margin-bottom: 10px;
        }

        .option-card p {
            color: #777;
            font-size: 14px;
        }

        /* Popups */
        .popup-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .popup {
            background: white;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            position: relative;
            z-index: 1001;
        }

        .popup h2 {
            color: #1A237E;
            margin-bottom: 20px;
        }

        .popup p {
            margin-bottom: 25px;
            color: #555;
        }

        .popup-btn {
            padding: 10px 25px;
            background: linear-gradient(to right, #FF6D00, #FF9100);
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .popup-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(255, 109, 0, 0.3);
        }

        /* Today's Trades Page */
        .trades-page {
            display: none;
            padding: 30px;
            position: relative;
        }

        .trades-page h2 {
            color: #1A237E;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        .trade-card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            position: relative;
            z-index: 1;
        }

        .trade-header {
            color: #1A237E;
            margin-bottom: 20px;
            font-weight: 600;
        }

        .trade-details {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }

        .detail-item {
            margin-bottom: 15px;
        }

        .detail-item h4 {
            color: #777;
            font-size: 14px;
            margin-bottom: 5px;
        }

        .detail-item p {
            color: #333;
            font-weight: 500;
        }

        .profit {
            color: #4CAF50 !important;
            font-weight: 600 !important;
        }

        .loss {
            color: #F44336 !important;
            font-weight: 600 !important;
        }

        .profit-total {
            margin-top: 20px;
            padding: 15px;
            background: #4CAF50;
            color: white;
            border-radius: 5px;
            text-align: center;
            font-weight: 600;
        }

        .loss-total {
            margin-top: 20px;
            padding: 15px;
            background: #F44336;
            color: white;
            border-radius: 5px;
            text-align: center;
            font-weight: 600;
        }

        /* P&L Summary */
        .pnl-summary {
            background: white;
            border-radius: 10px;
            padding: 25px;
            margin-top: 30px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            position: relative;
            z-index: 1;
        }

        .pnl-summary h3 {
            color: #1A237E;
            margin-bottom: 20px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }

        .pnl-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .pnl-stat {
            text-align: center;
        }

        .pnl-stat h4 {
            color: #777;
            font-size: 14px;
            margin-bottom: 5px;
        }

        .pnl-stat p {
            font-size: 18px;
            font-weight: 600;
        }

        .positive {
            color: #4CAF50;
        }

        .negative {
            color: #F44336;
        }

        /* Upgrade Plan Popup */
        .upgrade-features {
            text-align: left;
            margin: 20px 0;
        }

        .upgrade-features li {
            margin-bottom: 10px;
            color: #555;
        }

        .price-tag {
            font-size: 28px;
            font-weight: 700;
            color: #1A237E;
            margin: 20px 0;
        }

        .pay-btn {
            padding: 12px 30px;
            background: linear-gradient(to right, #FF6D00, #FF9100);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            margin-top: 15px;
            transition: all 0.3s;
        }

        .pay-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(255, 109, 0, 0.3);
        }

        /* Back Button */
        .back-btn {
            display: inline-block;
            margin-bottom: 20px;
            color: #1A237E;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
            z-index: 1;
        }

        .back-btn:hover {
            color: #0d47a1;
        }

        .back-btn i {
            margin-right: 5px;
        }

        /* Authorization Popup */
        .auth-popup {
            display: none;
        }

        .auth-message {
            margin-bottom: 20px;
            color: #555;
        }

        /* Script Activation Popup */
        .script-activation-popup {
            display: none;
        }

        /* Countdown Timer */
        .countdown {
            display: inline-block;
            background: #FF6D00;
            color: white;
            padding: 3px 8px;
            border-radius: 4px;
            font-weight: 600;
            font-size: 12px;
        }

        /* Fixed Broker Button */
        .fixed-broker-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            display: flex;
            align-items: center;
            background: rgba(26, 35, 126, 0.9);
            color: white;
            padding: 10px 15px;
            border-radius: 20px;
            cursor: pointer;
            z-index: 100;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .fixed-broker-btn .status-dot {
            width: 10px;
            height: 10px;
            background-color: #4CAF50;
            border-radius: 50%;
            margin-right: 8px;
        }
    </style>
</head>
<body>
    <!-- Watermark -->
    <div class="watermark">
        <div class="watermark-text">INDIA IT SOLUTIONS</div>
    </div>

    <!-- Login Page -->
    <div class="login-container" id="loginPage">
        <div class="login-box">
            <div class="logo">India IT Solutions</div>
            <h2>Login to Your Account</h2>
            <div class="input-group">
                <label for="username">Username</label>
                <input type="text" id="username" placeholder="Enter your username">
            </div>
            <div class="input-group">
                <label for="password">Password</label>
                <input type="password" id="password" placeholder="Enter your password">
            </div>
            <button class="login-btn" id="loginBtn">Login</button>
            <div class="forgot-password">Forgot Password?</div>
        </div>
    </div>

    <!-- Dashboard -->
    <div class="dashboard" id="dashboard">
        <div class="header">
            <div class="broker-container">
                <div class="broker-status" onclick="redirectToUpstox()">
                    <div class="status-dot"></div>
                    <span>UPSTOX Demat</span>
                </div>
                <div class="algo-toggle">
                    <span>Algo:</span>
                    <label class="switch">
                        <input type="checkbox" id="algoMasterSwitch">
                        <span class="slider"></span>
                    </label>
                </div>
            </div>
            <div class="user-profile" onclick="toggleProfileDropdown()">
                <span>Arjun</span>
                <div class="profile-avatar">A</div>
                <!-- Profile Dropdown -->
                <div class="profile-dropdown" id="profileDropdown">
                    <div class="user-info">
                        <div class="user-info-avatar">A</div>
                        <div class="user-details">
                            <h4>Arjun Sharma</h4>
                            <p>Premium Member</p>
                        </div>
                    </div>
                    <div class="subscription-status">
                        <h5>Subscription Status</h5>
                        <p>Your plan expires in <span class="countdown">28 days</span></p>
                    </div>
                    <ul class="profile-menu">
                        <li><a href="#"><i class="fas fa-user"></i> My Account</a></li>
                        <li><a href="#"><i class="fas fa-cog"></i> Settings</a></li>
                        <li><a href="#"><i class="fas fa-question-circle"></i> Help</a></li>
                        <li><a href="#"><i class="fas fa-sign-out-alt"></i> Logout</a></li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Scripts Control Section -->
        <div class="scripts-control">
            <h3>Scripts Control</h3>
            <div class="script-list">
                <div class="script-item">
                    <span class="script-name">NIFTY</span>
                    <div class="script-controls">
                        <input type="number" class="quantity-input" placeholder="Qty" min="1" onchange="handleQuantityChange(this)">
                        <label class="switch">
                            <input type="checkbox" disabled>
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
                <div class="script-item">
                    <span class="script-name">SENSEX</span>
                    <div class="script-controls">
                        <input type="number" class="quantity-input" placeholder="Qty" min="1" onchange="handleQuantityChange(this)">
                        <label class="switch">
                            <input type="checkbox" disabled>
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
                <div class="script-item">
                    <span class="script-name">BANKNIFTY</span>
                    <div class="script-controls">
                        <input type="number" class="quantity-input" placeholder="Qty" min="1" onchange="handleQuantityChange(this)">
                        <label class="switch">
                            <input type="checkbox" disabled>
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
                <div class="script-item">
                    <span class="script-name">BANKEX</span>
                    <div class="script-controls">
                        <input type="number" class="quantity-input" placeholder="Qty" min="1" onchange="handleQuantityChange(this)">
                        <label class="switch">
                            <input type="checkbox" disabled>
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
                <div class="script-item">
                    <span class="script-name">MIDCAPNIFTY</span>
                    <div class="script-controls">
                        <input type="number" class="quantity-input" placeholder="Qty" min="1" onchange="handleQuantityChange(this)">
                        <label class="switch">
                            <input type="checkbox" disabled>
                            <span class="slider"></span>
                        </label>
                    </div>
                </div>
            </div>
        </div>

        <div class="options-grid">
            <div class="option-card" onclick="showTradesPage()">
                <i class="fas fa-chart-line"></i>
                <h3>Today's Trades</h3>
                <p>View all trades executed today</p>
            </div>
            <div class="option-card" onclick="alert('Troubleshoot page will open')">
                <i class="fas fa-tools"></i>
                <h3>Troubleshoot</h3>
                <p>Resolve technical issues</p>
            </div>
            <div class="option-card" onclick="showUpgradePopup()">
                <i class="fas fa-rocket"></i>
                <h3>Upgrade Service</h3>
                <p>Upgrade to premium features</p>
            </div>
            <div class="option-card" onclick="showAuthPopup()">
                <i class="fas fa-rupee-sign"></i>
                <h3>Total P&L Till Date</h3>
                <p>View your overall profitability</p>
            </div>
        </div>

        <!-- Fixed Broker Button -->
        <div class="fixed-broker-btn" onclick="redirectToUpstox()">
            <div class="status-dot"></div>
            <span>UPSTOX Demat</span>
        </div>
    </div>

    <!-- Welcome Popup -->
    <div class="popup-overlay" id="welcomePopup">
        <div class="popup">
            <h2>Welcome <span style="color: #FF6D00;">Arjun</span></h2>
            <p>to India IT Solutions Algo Platform</p>
            <button class="popup-btn" onclick="closeWelcomePopup()">OK</button>
        </div>
    </div>

    <!-- Today's Trades Page -->
    <div class="trades-page" id="tradesPage">
        <div class="back-btn" onclick="backToDashboard()">
            <i class="fas fa-arrow-left"></i> Back to Dashboard
        </div>
        <h2>Trades Taken By Algo</h2>
        
        <!-- Trade 1 -->
        <div class="trade-card">
            <div class="trade-header">SENSEX 01 APR 2025 PE 77500</div>
            <div class="trade-details">
                <div class="detail-item">
                    <h4>Buying Time</h4>
                    <p>9:22 AM</p>
                </div>
                <div class="detail-item">
                    <h4>Buying Price</h4>
                    <p>₹234.15</p>
                </div>
                <div class="detail-item">
                    <h4>Quantity</h4>
                    <p>1400</p>
                </div>
                <div class="detail-item">
                    <h4>Exit Time</h4>
                    <p>9:39 AM</p>
                </div>
                <div class="detail-item">
                    <h4>Exit Price</h4>
                    <p>₹375.70</p>
                </div>
                <div class="detail-item">
                    <h4>Profit Booked</h4>
                    <p class="profit">₹198,370.00</p>
                </div>
            </div>
            <div class="profit-total">
                Trade Result: ₹198,370.00 Profit
            </div>
        </div>

        <!-- Trade 2 -->
        <div class="trade-card">
            <div class="trade-header">SENSEX 01 APR 2025 PE 78000</div>
            <div class="trade-details">
                <div class="detail-item">
                    <h4>Buying Time</h4>
                    <p>10:29 AM</p>
                </div>
                <div class="detail-item">
                    <h4>Buying Price</h4>
                    <p>₹161.65</p>
                </div>
                <div class="detail-item">
                    <h4>Quantity</h4>
                    <p>1400</p>
                </div>
                <div class="detail-item">
                    <h4>Exit Time</h4>
                    <p>10:52 AM</p>
                </div>
                <div class="detail-item">
                    <h4>Exit Price</h4>
                    <p>₹277.30</p>
                </div>
                <div class="detail-item">
                    <h4>Profit Booked</h4>
                    <p class="profit">₹161,910.00</p>
                </div>
            </div>
            <div class="profit-total">
                Trade Result: ₹161,910.00 Profit
            </div>
        </div>

        <!-- P&L Summary -->
        <div class="pnl-summary">
            <h3>Today's P&L Summary</h3>
            <div class="pnl-stats">
                <div class="pnl-stat">
                    <h4>Total Trades</h4>
                    <p>2</p>
                </div>
                <div class="pnl-stat">
                    <h4>Profitable Trades</h4>
                    <p class="positive">2</p>
                </div>
                <div class="pnl-stat">
                    <h4>Loss Making Trades</h4>
                    <p class="negative">0</p>
                </div>
                <div class="pnl-stat">
                    <h4>Gross Profit</h4>
                    <p class="positive">₹360,280.00</p>
                </div>
                <div class="pnl-stat">
                    <h4>Gross Loss</h4>
                    <p class="negative">₹0.00</p>
                </div>
                <div class="pnl-stat">
                    <h4>Net P&L</h4>
                    <p class="positive">₹360,280.00</p>
                </div>
            </div>
        </div>

        <!-- Fixed Broker Button -->
        <div class="fixed-broker-btn" onclick="redirectToUpstox()">
            <div class="status-dot"></div>
            <span>UPSTOX Demat</span>
        </div>
    </div>

    <!-- Upgrade Plan Popup -->
    <div class="popup-overlay" id="upgradePopup">
        <div class="popup">
            <h2>Upgrade to SuperPlatform</h2>
            <div class="price-tag">Only ₹99,999</div>
            
            <div class="upgrade-features">
                <p>SuperPlatform will offer you:</p>
                <ul>
                    <li>7+ High-Accuracy Strategies</li>
                    <li>Gap & Go Momentum Strategy (85% Accuracy)</li>
                    <li>Trend Reversal AI Detection (90% Accuracy)</li>
                    <li>Overnight Position Analyzer</li>
                    <li>Real-time Alerts with Push Notifications</li>
                    <li>24/7 Priority Support</li>
                    <li>Advanced Risk Management Tools</li>
                </ul>
            </div>
            
            <button class="pay-btn">Pay Now</button>
            <button class="popup-btn" onclick="closeUpgradePopup()" style="background: #ccc; color: #333; margin-left: 10px;">Later</button>
        </div>
    </div>

    <!-- Authorization Popup -->
    <div class="popup-overlay auth-popup" id="authPopup">
        <div class="popup">
            <h2>Authorization Required</h2>
            <div class="auth-message">
                <p>You need admin authorization to access the Total P&L data.</p>
                <p>Please contact your account manager for access.</p>
            </div>
            <button class="popup-btn" onclick="closeAuthPopup()">OK</button>
        </div>
    </div>

    <!-- Script Activation Popup -->
    <div class="popup-overlay script-activation-popup" id="scriptActivationPopup">
        <div class="popup">
            <h2>Script Activated</h2>
            <p id="activationMessage"></p>
            <button class="popup-btn" onclick="closeScriptActivationPopup()">OK</button>
        </div>
    </div>

    <script>
        // Login function - FIXED
        document.getElementById('loginBtn').addEventListener('click', function() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (username && password) {
                document.getElementById('loginPage').style.display = 'none';
                document.getElementById('dashboard').style.display = 'block';
                document.getElementById('welcomePopup').style.display = 'flex';
            } else {
                alert('Please enter both username and password');
            }
        });

        // Close welcome popup
        function closeWelcomePopup() {
            document.getElementById('welcomePopup').style.display = 'none';
        }

        // Show trades page
        function showTradesPage() {
            document.getElementById('dashboard').style.display = 'none';
            document.getElementById('tradesPage').style.display = 'block';
        }

        // Back to dashboard
        function backToDashboard() {
            document.getElementById('tradesPage').style.display = 'none';
            document.getElementById('dashboard').style.display = 'block';
        }

        // Show upgrade popup
        function showUpgradePopup() {
            document.getElementById('upgradePopup').style.display = 'flex';
        }

        // Close upgrade popup
        function closeUpgradePopup() {
            document.getElementById('upgradePopup').style.display = 'none';
        }

        // Show authorization popup
        function showAuthPopup() {
            document.getElementById('authPopup').style.display = 'flex';
        }

        // Close authorization popup
        function closeAuthPopup() {
            document.getElementById('authPopup').style.display = 'none';
        }

        // Show script activation popup
        function showScriptActivationPopup(scriptName, quantity) {
            document.getElementById('activationMessage').textContent = 
                `${quantity} quantity set for ${scriptName} trading`;
            document.getElementById('scriptActivationPopup').style.display = 'flex';
        }

        // Close script activation popup
        function closeScriptActivationPopup() {
            document.getElementById('scriptActivationPopup').style.display = 'none';
        }

        // Redirect to Upstox
        function redirectToUpstox() {
            window.open('https://upstox.com', '_blank');
        }

        // Toggle profile dropdown
        function toggleProfileDropdown() {
            document.getElementById('profileDropdown').classList.toggle('active');
        }

        // Close dropdown when clicking outside
        document.addEventListener('click', function(event) {
            const profileDropdown = document.getElementById('profileDropdown');
            const profileAvatar = document.querySelector('.profile-avatar');
            
            if (!profileAvatar.contains(event.target) && !profileDropdown.contains(event.target)) {
                profileDropdown.classList.remove('active');
            }
        });

        // Handle quantity input change
        function handleQuantityChange(input) {
            const scriptItem = input.closest('.script-item');
            const switchInput = scriptItem.querySelector('.switch input');
            const scriptName = scriptItem.querySelector('.script-name').textContent;
            
            if (input.value && input.value > 0) {
                switchInput.disabled = false;
                switchInput.checked = true;
                showScriptActivationPopup(scriptName, input.value);
            } else {
                switchInput.checked = false;
                switchInput.disabled = true;
            }
        }

        // Initialize master algo switch
        document.getElementById('algoMasterSwitch').addEventListener('change', function() {
            if (this.checked) {
                alert('Algo trading has been enabled');
            } else {
                alert('Algo trading has been disabled');
            }
        });

        // Initialize switches
        document.querySelectorAll('.switch input').forEach(switchInput => {
            const event = new Event('change');
            switchInput.dispatchEvent(event);
        });
    </script>
</body>
</html>
