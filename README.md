# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh


CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    phone VARCHAR(20),
    password VARCHAR(255)
);
CREATE TABLE bonds (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    bond_name VARCHAR(255),
    issue_date DATE,
    maturity_date DATE,
    principal_amount DECIMAL(15,2),
    coupon_rate DECIMAL(5,2),
    created_at DATETIME,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
CREATE TABLE cash_holdings (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    amount DECIMAL(15,2),
    monthly_interest DECIMAL(5,2),
    start_date DATE,
    type VARCHAR(50),
    bank VARCHAR(100),
    created_at DATETIME,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
CREATE TABLE gold_holdings (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    quantity_in_grams DECIMAL(10,4),
    purchase_price_per_gram DECIMAL(10,2),
    purchase_date DATE,
    created_at DATETIME,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
CREATE TABLE stocks (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    name VARCHAR(100),
    price DECIMAL(10,2),
    quantity DECIMAL(10,4),
    created_at DATETIME,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
