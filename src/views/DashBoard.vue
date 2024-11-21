<template>
  <div class="dashboard-container">
    <!-- Sidebar -->
    <div class="sidebar">
      <div class="logo-container">
        <img src="@/assets/logo.png" alt="kanban-logo" class="logo-img" />
        <div class="logo-text">KANBAN</div>
      </div>
      
      <nav class="menu">
        <router-link to="/dashboard">
          <i class="fas fa-home icon"></i> Dashboard
        </router-link>
        <router-link to="/inventario">
          <i class="fas fa-box icon"></i> Inventory
        </router-link>
        <a href="#"><i class="fas fa-chart-line icon"></i> Reports</a>
        <a href="#"><i class="fas fa-users icon"></i> Suppliers</a>
        <a href="#"><i class="fas fa-truck icon"></i> Orders</a>
        <a href="#"><i class="fas fa-cogs icon"></i> Manage</a>
        <a href="#"><i class="fas fa-store icon"></i> Store</a>
      </nav>

      <div class="bottom-links">
        <a href="#"><i class="fas fa-cog icon"></i> Settings</a>
        <a href="#"><i class="fas fa-sign-out-alt icon"></i> Log Out</a>
      </div>
    </div>

    <!-- Main Content -->
    <div class="main-content">
      <header>
        <input type="text" placeholder="Search product, supplier, order" />
        <div class="user-info">
          <img src="@/assets/logo.png" alt="Logo" />
        </div>
      </header>

      <div class="dashboard-cards">
        <div class="card">
          <h3>Sales Overview</h3>
          <p>₹ 832 Sales | ₹ 18,300 Revenue | ₹ 868 Profit | ₹ 17,432 Cost</p>
        </div>
        <div class="card">
          <h3>Purchase Overview</h3>
          <p>82 Purchases | ₹ 13,573 Cost | 5 Cancellations | ₹ 17,432 Returns</p>
        </div>
        <div class="card">
          <h3>Inventory Summary</h3>
          <p>868 Quantity in Hand | 200 To be received</p>
        </div>
        <div class="card">
          <h3>Product Summary</h3>
          <p>31 Suppliers | 21 Categories</p>
        </div>
        <div class="card">
          <h3>Order Summary</h3>
          <p>Graph Placeholder</p>
        </div>
      </div>

      <div class="charts">
        <div class="chart">Sales & Purchase Chart Placeholder</div>

        <div class="top-selling">
          <h3>Top Selling Stock</h3>
          <table>
            <tr>
              <th>Name</th>
              <th>Sold Quantity</th>
              <th>Remaining Quantity</th>
              <th>Price</th>
            </tr>
            <tr>
              <td>Surf Excel</td>
              <td>30</td>
              <td>12</td>
              <td>₹ 100</td>
            </tr>
            <tr>
              <td>Rin</td>
              <td>21</td>
              <td>15</td>
              <td>₹ 207</td>
            </tr>
            <tr>
              <td>Parle G</td>
              <td>19</td>
              <td>17</td>
              <td>₹ 105</td>
            </tr>
          </table>
        </div>

        <div class="low-quantity">
          <h3>Low Quantity Stock</h3>
          <p>Tata Salt - Remaining Quantity: 10 Packets (Low)</p>
          <p>Lays - Remaining Quantity: 15 Packets (Low)</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DashBoard',
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}

body {
  display: flex;
  background-color: #f0f2f5;
  color: #333;
}

.dashboard-container {
  display: flex;
  flex: 1;
}

.sidebar {
  width: 250px;
  background-color: #fff;
  border-right: 1px solid #ddd;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
}

.menu {
  flex-grow: 1;
}

.logo-container {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
}

.logo-img {
  width: 40px;
  height: auto;
}

.logo-text {
  font-size: 24px;
  font-weight: bold;
  color: #1c74ef;
}

.sidebar nav a,
.bottom-links a {
  display: block;
  color: #333;
  padding: 15px 10px;
  text-decoration: none;
  margin-bottom: 5px;
  border-radius: 5px;
}

.sidebar nav a.active,
.sidebar nav a:hover,
.bottom-links a:hover {
  background-color: #f0f2f5;
  color: #1c74ef;
}

.bottom-links {
  margin-top: auto;
}

.icon {
  color: #1c74ef;
  padding-right: 10px;
  font-size: 16px;
  vertical-align: middle;
}

.main-content {
  flex-grow: 1;
  padding: 20px;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

header input[type="text"] {
  padding: 10px;
  width: 300px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.user-info img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.dashboard-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
  margin-bottom: 20px;
}

.card {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.card h3 {
  font-size: 16px;
  color: #333;
  margin-bottom: 10px;
}

.card p {
  font-size: 14px;
  color: #666;
}

.charts {
  display: flex;
  gap: 20px;
}

.chart,
.top-selling,
.low-quantity {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  flex: 1;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}

table th,
table td {
  padding: 10px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

.low-quantity p {
  font-size: 14px;
  color: #ff5e57;
  margin: 5px 0;
}
</style>
