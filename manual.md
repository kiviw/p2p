# Bunker Marketplace User Manual

## Introduction

Bunker Marketplace is a peer-to-peer marketplace designed for both digital and physical goods. It operates on an Ubuntu22 server and is built using Python and Flask. This user manual will guide you through the installation process, explain the main functions of the software, and provide instructions on how to use it effectively.

## Table of Contents

1. Installation
2. Main Functions
3. Usage Instructions
4. Troubleshooting
5. Frequently Asked Questions (FAQs)

## 1. Installation

To install Bunker Marketplace, follow these steps:

1. Clone the repository to your server's `/var/www/html/` folder:

   ```
   git clone https://github.com/your_username/bunker-marketplace.git /var/www/html/
   ```

2. Install the required dependencies by running the following command:

   ```
   pip install -r requirements.txt
   ```

3. Configure the MySQL database by importing the `database.sql` file:

   ```
   mysql -u your_mysql_user -p your_mysql_password bunker_db < /var/www/html/database.sql
   ```

4. Update the configuration file `config.py` with your MySQL credentials:

   ```python
   MYSQL_HOST = 'localhost'
   MYSQL_USER = 'your_mysql_user'
   MYSQL_PASSWORD = 'your_mysql_password'
   MYSQL_DB = 'bunker_db'
   ```

5. Start the Bunker Marketplace application:

   ```
   python main.py
   ```

6. Access the marketplace by opening your web browser and navigating to `http://your_server_domain/`.

## 2. Main Functions

Bunker Marketplace offers the following main functions:

- User Registration: Users can create an account by providing a username, password, and captcha.
- User Login: Registered users can log in to their accounts using their credentials.
- Dashboard: Users can view their account details, including their Monero subaddress and balance.
- Product Listing: Sellers can upload products with details such as name, description, price in USD, and category.
- Dual Pricing: Products are displayed with dual pricing in both Monero and USD.
- Monero Transactions: All transactions are conducted using Monero, with unique subaddresses for each user.
- Monero Balance: Users can view their Monero account balance on the marketplace.
- CoinGecko Integration: The marketplace fetches live Monero to USD conversion rates from the CoinGecko API.
- Withdrawals: Users can request withdrawals to their Monero addresses, which are manually processed by the admin.
- Deposits: Deposits are automatically credited to user accounts after at least 2 confirmations.
- Commission: A commission of 8 percent is charged to the buyer after a sale is completed.
- Buyer-Seller Messaging: Messaging between buyers and sellers is encrypted using PGP tied to user registrations.
- Admin Dashboard: The admin has control over various aspects of the marketplace, including user management, withdrawal requests, and product categories.
- Forum: An inclusive forum is incorporated for user discussions.

## 3. Usage Instructions

### User Registration

1. Open the Bunker Marketplace website.
2. Click on the "Register" link.
3. Fill in the registration form with your desired username, password, and captcha.
4. Click on the "Register" button to create your account.

### User Login

1. Open the Bunker Marketplace website.
2. Click on the "Login" link.
3. Enter your username and password.
4. Click on the "Login" button to access your account.

### Dashboard

1. After logging in, you will be redirected to the dashboard.
2. The dashboard displays your Monero subaddress and balance.
3. You can view your account details and perform various actions from the dashboard.

### Product Listing

1. From the dashboard, click on the "Sell" or "Create Product" button.
2. Fill in the product details, including name, description, price in USD, and category.
3. Upload an image of the product.
4. Click on the "Submit" or "Create" button to list the product.

### Dual Pricing

1. On the product listing page, you will see the price displayed in both Monero and USD.
2. The Monero price is calculated based on the current live price fetched from the CoinGecko API.

### Withdrawals

1. From the dashboard, navigate to the "Withdrawals" section.
2. Enter your Monero address and the amount you wish to withdraw.
3. Submit the withdrawal request.
4. The admin will manually process the withdrawal request.

### Admin Dashboard

1. Access the admin dashboard by visiting `http://your_server_domain/admin`.
2. Log in using the admin credentials (default: username - mrbunker, password - 12345678).
3. From the admin dashboard, you can manage users, handle withdrawal requests, and edit marketplace settings.

## 4. Troubleshooting

If you encounter any issues while using Bunker Marketplace, please refer to the following troubleshooting steps:

1. Ensure that all the installation steps were followed correctly.
2. Check the server logs for any error messages.
3. Make sure the MySQL database is running and accessible.
4. Verify that the Monero wallet RPC is running smoothly on the installation server.
5. Double-check the configuration file (`config.py`) for correct MySQL credentials.
6. Clear your browser cache and try accessing the marketplace again.
7. If the issue persists, please contact our support team for further assistance.

## 5. Frequently Asked Questions (FAQs)

**Q: Can I change the admin credentials?**

A: Yes, you can change the admin credentials from the admin dashboard. Navigate to the "Admin Settings" section and update the username and password.

**Q: How often does the marketplace fetch live Monero to USD conversion rates?**

A: The marketplace fetches live rates every minute using AJAX. The prices are updated once per minute to ensure accuracy.

**Q: Can I add new categories to the marketplace?**

A: Yes, you can add new categories from the admin dashboard. Navigate to the "Categories" section and click on the "Add Category" button.

**Q: How do I change the app icon and logo?**

A: You can change the app icon and logo from the admin dashboard. Navigate to the "Admin Settings" section and upload the desired images.

**Q: How do I access the inclusive forum for user discussions?**

A: The forum can be accessed from the main navigation menu on the marketplace website. Click on the "Forum" link to participate in user discussions.

For any further questions or assistance, please contact our support team.

---

Congratulations! You are now ready to use Bunker Marketplace. If you have any additional questions or need further assistance, please don't hesitate to reach out to our support team. Enjoy your peer-to-peer buying and selling experience on Bunker Marketplace!

```