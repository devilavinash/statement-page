<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transaction History</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.0/css/bootstrap.min.css">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">

  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .balance {
      font-size: 1.5rem;
      margin: 20px 0;
    }
    .btn-container {
      display: flex;
      justify-content: center;
      gap: 15px;
    }
    .transaction-history {
      margin-top: 20px;
    }
    .transaction-item {
      display: flex;
      justify-content: space-between;
      padding: 10px;
      border-bottom: 1px solid #ddd;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 class="text-center mt-4">Transaction History</h1>

    <div class="text-center balance">
      <strong>Available Balance:</strong> Rs.<%= balance %> /-
    </div>

    <div class="btn-container">
      <button class="btn btn-success"><i class="fa-solid fa-money-bill">Add Money</i></button>
      <button class="btn btn-warning"><i class=""></i>Withdrawal Money</button>
    </div>

    <div class="transaction-history">
      <% transactions.forEach(transaction => { %>
        <div class="transaction-item">
          <div>
            <strong><%= transaction.title %></strong>
            <small class="text-muted d-block"><%= transaction.date %></small>
          </div>
          <div>
            <strong 
              class="<%= transaction.amount.startsWith('+') ? 'text-success' : 'text-danger' %>">
              <%= transaction.amount %>
            </strong>
            <small class="text-muted d-block">Closing Balance: Rs. <%= transaction.closingBalance %></small>
          </div>
        </div>
      <% }) %>
    </div>
  </div>
</body>
</html>
