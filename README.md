<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Railway Component Details</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f9;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #003366;
    }
    .card {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 400px;
      margin: auto;
      box-shadow: 0px 4px 10px rgba(0,0,0,0.2);
    }
    .detail {
      margin: 10px 0;
      font-size: 18px;
    }
    input, button {
      padding: 10px;
      margin-top: 15px;
      font-size: 16px;
    }
    button {
      background: #003366;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #0055a5;
    }
  </style>
</head>
<body>
  <h1>Railway Component Tracker</h1>

  <div class="card">
    <h2>Enter Lot Number</h2>
    <input type="text" id="lotInput" placeholder="e.g. LOT12345">
    <button onclick="getDetails()">Get Details</button>
    <div id="details"></div>
  </div>

  <script>
    // Sample Database (You can later replace this with real DB data)
    const components = {
      "LOT12345": {
        name: "Elastic Rail Clip",
        manufacturer: "ABC Steel Works",
        date: "2025-01-12",
        batch: "Batch A1",
        certification: "Approved by RDSO"
      },
      "LOT67890": {
        name: "Rail Pad",
        manufacturer: "XYZ Polymers Ltd.",
        date: "2025-02-08",
        batch: "Batch B2",
        certification: "Pending"
      },
      "LOT24680": {
        name: "Concrete Sleeper",
        manufacturer: "RailInfra Pvt. Ltd.",
        date: "2025-03-20",
        batch: "Batch C3",
        certification: "Approved"
      }
    };

    function getDetails() {
      const lot = document.getElementById("lotInput").value.trim();
      const detailsDiv = document.getElementById("details");

      if (components[lot]) {
        const c = components[lot];
        detailsDiv.innerHTML = `
          <div class="detail"><b>Component:</b> ${c.name}</div>
          <div class="detail"><b>Lot Number:</b> ${lot}</div>
          <div class="detail"><b>Manufacturer:</b> ${c.manufacturer}</div>
          <div class="detail"><b>Date of Manufacturing:</b> ${c.date}</div>
          <div class="detail"><b>Batch:</b> ${c.batch}</div>
          <div class="detail"><b>Certification:</b> ${c.certification}</div>
        `;
      } else {
        detailsDiv.innerHTML = `<p style="color:red;">Lot Number not found.</p>`;
      }
    }
  </script>
</body>
</html>
