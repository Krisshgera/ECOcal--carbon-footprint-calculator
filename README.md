                                                 //FRONTEND//
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Notifications</title>
  <style>
    /* Basic styles for layout */
    body {
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f0f4f8;
      color: #333;
    }

    .header {
      background: linear-gradient(135deg, #4caf50, #2e7d32);
      color: white;
      padding: 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
      border-bottom: 4px solid #2e7d32;
      position: relative;
    }

    .header h1 {
      margin: 0;
      font-size: 2em;
      font-weight: bold;
    }

    .header h2 {
      margin: 0;
      font-size: 1.4em;
      font-weight: normal;
    }

    .dropdown {
      position: relative;
      display: inline-block;
    }

    .dropbtn {
      background-color: #2e7d32;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1em;
      font-weight: bold;
      transition: background-color 0.3s;
    }

    .dropbtn:hover {
      background-color: #1b5e20;
    }

    .dropdown-content {
      display: none;
      position: absolute;
      top: 100%;
      right: 0;
      background-color: white;
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
      border-radius: 8px;
      z-index: 1;
      min-width: 200px;
    }

    .dropdown-content a {
      color: #333;
      padding: 12px 16px;
      text-decoration: none;
      display: block;
      font-size: 1em;
      transition: background-color 0.3s;
    }

    .dropdown-content a:hover {
      background-color: #f1f8f4;
    }

    .dropdown:hover .dropdown-content {
      display: block;
    }

    .content {
      padding: 20px;
      max-width: 1000px;
      margin: auto;
    }

    .notification {
      background-color: white;
      border-radius: 12px;
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
      padding: 20px;
      margin-bottom: 20px;
      position: relative;
      transition: background-color 0.3s, transform 0.3s, box-shadow 0.3s;
      border-left: 8px solid #4caf50;
      overflow: hidden;
    }

    .notification::before {
      content: '';
      position: absolute;
      top: 0;
      left: -10px;
      width: 10px;
      height: 100%;
      background-color: #4caf50;
      border-top-right-radius: 12px;
      border-bottom-right-radius: 12px;
    }

    .notification:hover {
      background-color: #eaf4e9;
      transform: translateY(-5px);
      box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
    }

    .notification p {
      margin: 0;
      font-size: 1em;
      line-height: 1.5;
    }

    .notification .user {
      font-weight: bold;
      color: #2e7d32;
    }

    .notification .timestamp {
      color: #666;
      font-size: 0.9em;
    }

    .notification .message {
      margin-top: 10px;
    }

    .notification a {
      color: #4caf50;
      text-decoration: none;
      font-weight: bold;
      border-bottom: 2px solid #4caf50;
      transition: color 0.3s, border-bottom 0.3s;
    }

    .notification a:hover {
      color: #2e7d32;
      border-bottom: 2px solid transparent;
    }

    @media (max-width: 600px) {
      .header {
        flex-direction: column;
        align-items: flex-start;
      }

      .header h1,
      .header h2 {
        font-size: 1.5em;
      }

      .dropdown-content {
        min-width: 150px;
      }

      .notification {
        padding: 15px;
      }
    }
  </style>
</head>

<body>
  <header class="header">
    <h1>Notifications</h1>
    <h2>Latest Updates</h2>
    <div class="dropdown">
      <button class="dropbtn">Menu</button>
      <div class="dropdown-content">
        <a href="#personal-profile">Personal Profile</a>
        <a href="leaderboardhackathon.html">Local Leaderboard</a>
        <a href="calculatorhackathon.html">Carbon Calculator</a>
        <a href="#carbon-footprint-map">Carbon Footprint Map</a>
        <a href="#additional-resources">Additional Resources</a>
      </div>
    </div>
  </header>
  <main class="content">
    <div class="notification">
      <p class="user">@algore <span class="timestamp" id="timestamp1"></span></p>
      <p class="message">Gore unveils $300m climate ads😮 <a
          href="https://www.theguardian.com/world/2008/mar/31/algore.uselections08.climate" target="_blank">Read
          more</a></p>
    </div>
    <div class="notification">
      <p class="user">United Nations <span class="timestamp" id="timestamp2"></span></p>
      <p class="message">Actions for a healthy planet!🌍 <a
          href="https://www.un.org/en/actnow/ten-actions#:~:text=Walk%2C%20bike%20or%20take%20public%20transport&text=For%20longer%20distances%2C%20consider%20taking,a%20lifestyle%20using%20a%20car."
          target="_blank">Read more</a></p>
    </div>
    <div class="notification">
      <p class="user">EcoCart <span class="timestamp" id="timestamp3"></span></p>
      <p class="message">Hello! We enhance Your Tourism Marketing Strategies With Climate Contribution. We are so
        excited to join ECOcal!✈️ <a href="https://ecocart.io/sustainable-tourism-marketing-strategies/"
          target="_blank">Read more</a></p>
    </div>
    <div class="notification">
      <p class="user">@ECOcal <span class="timestamp" id="timestamp4"></span></p>
      <p class="message">Here's an insight into our Github, <a
          href="https://github.com/Krisshgera/ECOcal--carbon-footprint-calculator/blob/main/ECOcal.java"
          target="_blank">Know more about our Code</a></p>
    </div>
  </main>
  <script>
    // Function to calculate and display time since notification sent
    function getTimeSince(sentTime) {
      const now = new Date();
      const then = new Date(sentTime);
      const diffMs = Math.abs(now - then);
      const diffMins = Math.round(diffMs / (1000 * 60));
      const diffHours = Math.round(diffMins / 60);
      const diffDays = Math.round(diffHours / 24);

      let message;
      if (diffDays > 0) {
        message = ${diffDays} day${diffDays > 1 ? 's' : ''};
      } else if (diffHours > 0) {
        message = ${diffHours} hour${diffHours > 1 ? 's' : ''};
      } else {
        message = ${diffMins} minute${diffMins > 1 ? 's' : ''};
      }
      return message + " ago";
    }

    // Get notification sent times (replace with actual data fetching logic)
    const sentTimes = ["2024-07-20T12:00:00", "2024-07-20T11:00:00", "2024-07-20T10:00:00", "2024-07-20T09:00:00"];

    // Update timestamps
    const timestamps = document.querySelectorAll(".notification .timestamp");
    for (let i = 0; i < timestamps.length; i++) {
      timestamps[i].textContent = getTimeSince(sentTimes[i]);
    }
  </script>
</body>

</html>









                                                                
                                        
                                                                 //CARBON CALCULATOR//
                                                                 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carbon Footprint Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(to bottom, #e0f2f1, #b9fbc0);
        }
        h1 {
            margin: 20px;
            color: #2e7d32;
            font-size: 36px;
            font-weight: bold;
        }
        .calculator {
            width: 100%;
            max-width: 450px;
            padding: 30px;
            background: #ffffff;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            box-sizing: border-box;
        }
        .calculator h2 {
            margin: 0;
            margin-bottom: 20px;
            color: #2e7d32;
            font-size: 28px;
            font-weight: bold;
        }
        .input-group {
            margin-bottom: 20px;
        }
        .input-group label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: bold;
        }
        .input-group input {
            width: calc(100% - 20px);
            padding: 12px;
            border: 1px solid #a5d6a7;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 16px;
        }
        .input-group input:focus {
            border-color: #66bb6a;
            outline: none;
            box-shadow: 0 0 8px rgba(0, 150, 0, 0.3);
        }
        .calculate-btn {
            display: block;
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #66bb6a, #2e7d32);
            color: white;
            text-align: center;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            transition: background 0.3s, transform 0.2s;
        }
        .calculate-btn:hover {
            background: linear-gradient(135deg, #2e7d32, #66bb6a);
            transform: scale(1.03);
        }
        .calculate-btn:active {
            background: #1b5e20;
            transform: scale(0.98);
        }
        .result {
            margin-top: 20px;
            padding: 15px;
            background: #f1f8e9;
            border: 1px solid #d0e9c6;
            border-radius: 8px;
            color: #2e7d32;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h1>CARBON CALCULATOR</h1>
    <div class="calculator">
        <div class="input-group">
            <label for="transport">Did you use any transportation today? (yes/no):</label>
            <input type="text" id="transport" placeholder="Enter 'yes' or 'no'">
        </div>
        <div class="input-group">
            <label for="distance">If yes, how far did you travel (in kilometres)?:</label>
            <input type="number" id="distance" placeholder="Enter distance travelled">
        </div>
        <div class="input-group">
            <label for="electricity">Electricity usage today (in kWh):</label>
            <input type="number" id="electricity" placeholder="Enter electricity used">
        </div>
        <div class="input-group">
            <label for="beef">Beef consumed per day (in grams):</label>
            <input type="number" id="beef" placeholder="Enter beef consumed">
        </div>
        <div class="input-group">
            <label for="pork">Pork consumed per day (in grams):</label>
            <input type="number" id="pork" placeholder="Enter pork consumed">
        </div>
        <div class="input-group">
            <label for="chicken">Chicken consumed per day (in grams):</label>
            <input type="number" id="chicken" placeholder="Enter chicken consumed">
        </div>
        <div class="input-group">
            <label for="fish">Fish consumed per day (in grams):</label>
            <input type="number" id="fish" placeholder="Enter fish consumed">
        </div>
        <button class="calculate-btn" onclick="calculateCarbonFootprint()">Calculate</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateCarbonFootprint() {
            const PETROL_SEDAN_EMISSION = 143;
            const DIESEL_SEDAN_EMISSION = 164;
            const ELECTRIC_CAR_EMISSION = 0;
            const MOTORCYCLE_EMISSION = 88;
            const BUS_EMISSION = 104;
            const ELECTRICITY_EMISSION = 0.233;
            const BEEF_EMISSION_FACTOR = 0.027;
            const PORK_EMISSION_FACTOR = 0.012;
            const CHICKEN_EMISSION_FACTOR = 0.0069;
            const FISH_EMISSION_FACTOR = 0.005;
            const AVERAGE_CARBON_FOOTPRINT = 2000;

            let dailyCarbonFootprint = 0;

            const transportUsed = document.getElementById('transport').value.trim().toLowerCase();
            if (transportUsed === 'yes') {
                const transportType = prompt("What type of transportation did you use? (car, motorcycle, bus):").trim().toLowerCase();
                const distance = parseFloat(document.getElementById('distance').value);
                dailyCarbonFootprint += calculateTransportationCarbonFootprint(transportType, distance);
            }

            const electricityUsed = parseFloat(document.getElementById('electricity').value);
            dailyCarbonFootprint += calculateElectricityCarbonFootprint(electricityUsed);

            dailyCarbonFootprint += parseFloat(document.getElementById('beef').value) * BEEF_EMISSION_FACTOR;
            dailyCarbonFootprint += parseFloat(document.getElementById('pork').value) * PORK_EMISSION_FACTOR;
            dailyCarbonFootprint += parseFloat(document.getElementById('chicken').value) * CHICKEN_EMISSION_FACTOR;
            dailyCarbonFootprint += parseFloat(document.getElementById('fish').value) * FISH_EMISSION_FACTOR;

            const estimateType = prompt("Would you like a daily or monthly estimate?").trim().toLowerCase();
            const annualMultiplier = estimateType === 'monthly' ? 12 : 365;
            const yearlyFootprint = dailyCarbonFootprint * annualMultiplier;

            const resultElement = document.getElementById('result');
            resultElement.innerHTML = `<strong>Total daily emissions:</strong> ${dailyCarbonFootprint.toFixed(2)} kg CO2<br>
                                        <strong>Estimated yearly emissions:</strong> ${yearlyFootprint.toFixed(2)} kg CO2<br>`;

            if (yearlyFootprint > AVERAGE_CARBON_FOOTPRINT) {
                resultElement.innerHTML += "<strong>Suggestions to reduce your carbon footprint:</strong><br>" +
                    "1. Use energy-efficient appliances.<br>" +
                    "2. Opt for public transport or biking.<br>" +
                    "3. Reduce meat consumption.";
            } else {
                resultElement.innerHTML += "<strong>Great job!</strong> Your emissions are below the average. Keep up the good work!";
            }
        }

        function calculateTransportationCarbonFootprint(transportType, distance) {
            switch (transportType) {
                case 'car':
                    const carType = prompt("What type of car did you use? (petrol sedan, diesel sedan, electric):").trim().toLowerCase();
                    return calculateCarCarbonFootprint(carType, distance);
                case 'motorcycle':
                    return distance * MOTORCYCLE_EMISSION / 1000;
                case 'bus':
                    return distance * BUS_EMISSION / 1000;
                default:
                    alert("Invalid transportation type.");
                    return 0;
            }
        }

        function calculateCarCarbonFootprint(carType, distance) {
            switch (carType) {
                case 'petrol sedan': return distance * PETROL_SEDAN_EMISSION / 1000;
                case 'diesel sedan': return distance * DIESEL_SEDAN_EMISSION / 1000;
                case 'electric': return distance * ELECTRIC_CAR_EMISSION / 1000;
                default: alert("Invalid car type."); return 0;
            }
        }

        function calculateElectricityCarbonFootprint(electricityUsed) {
            return electricityUsed * ELECTRICITY_EMISSION;
        }
    </script>
</body>
</html>


                                                                //LEADERBOARD//
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Leaderboard</title>
  <style>
    /* Style the entire page */
    body {
      background-color: #f0f4f8; /* Light background */
      margin: 0;
      padding: 0;
      font-family: 'Arial', sans-serif;
      color: #333;
    }

    /* Style the header */
    .header {
      background: linear-gradient(135deg, #2e7d32, #66bb6a); /* Green gradient */
      color: #fff;
      padding: 20px;
      text-align: center;
      font-size: 28px; /* Larger header font size */
      border-bottom: 5px solid #1b5e20; /* Darker green bottom border */
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Shadow effect */
      font-weight: bold;
    }

    /* Style the leaderboard table */
    .leaderboard {
      width: 90%;
      max-width: 900px;
      margin: 30px auto; /* Center table and add space from top/bottom */
      border-collapse: collapse;
      background-color: #ffffff; /* White background for table */
      border-radius: 12px; /* Rounded corners for the table */
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Subtle shadow effect */
      overflow: hidden;
    }

    .leaderboard, .leaderboard th, .leaderboard td {
      border: 1px solid #a5d6a7; /* Light green border */
      padding: 15px; /* Cell padding */
      text-align: left;
    }

    .leaderboard th {
      background: linear-gradient(135deg, #a5d6a7, #81c784); /* Light green gradient */
      color: #fff; /* White text */
      font-weight: bold;
      text-transform: uppercase; /* Uppercase headers */
      border-bottom: 2px solid #66bb6a; /* Slightly darker green bottom border */
    }

    /* Style for table rows */
    .leaderboard tr:nth-child(even) {
      background-color: #f9fbe7; /* Alternate row color */
    }

    .leaderboard tr:hover {
      background-color: #e8f5e9; /* Hover effect */
      transform: scale(1.01); /* Slight scale effect */
    }

    /* Responsive styling for smaller screens */
    @media (max-width: 600px) {
      .header {
        font-size: 20px;
        padding: 15px;
      }

      .leaderboard {
        width: 100%;
        font-size: 14px;
      }
    }

    /* Style the subheading */
    .subheading {
      text-align: center;
      font-size: 18px;
      margin-top: 10px; /* Adjusted margin */
      color: #666;
    }
  </style>
</head>
<body>
  <div class="header">Leaderboard</div>
  <div class="subheading">(Least daily carbon emission)</div>
  <table class="leaderboard">
    <tr>
      <th>Rank</th>
      <th>Name</th>
      <th>Score</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Paarth Yadav</td>
      <td>5kg CO2</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Parth Batra</td>
      <td>7kg CO2</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Krissh Gera</td>
      <td>12kg CO2</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Parth Somani</td>
      <td>17kg CO2</td>
    </tr>
  </table>
</body>
</html>



                                                                //BACKEND//
                                                                // Source code recreated from a .class file by IntelliJ IDEA
// (powered by FernFlower decompiler)
//

import java.awt.Component;
import java.awt.LayoutManager;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.SwingUtilities;

public class Main extends JFrame {
    private static final double PETROL_SEDAN_EMISSION = 143.0;
    private static final double DIESEL_SEDAN_EMISSION = 164.0;
    private static final double ELECTRIC_CAR_EMISSION = 0.0;
    private static final double MOTORCYCLE_EMISSION = 88.0;
    private static final double BUS_EMISSION = 104.0;
    private static final double ELECTRICITY_EMISSION = 0.233;
    private static final double BEEF_EMISSION_FACTOR = 27.0;
    private static final double PORK_EMISSION_FACTOR = 12.0;
    private static final double CHICKEN_EMISSION_FACTOR = 6.9;
    private static final double FISH_EMISSION_FACTOR = 5.0;
    private static final double AVERAGE_CARBON_FOOTPRINT = 2000.0;
    private static final String DATA_FILE = "carbon_footprint_data.txt";
    private JTextField transportField;
    private JTextField distanceField;
    private JTextField electricityField;
    private JTextField beefField;
    private JTextField porkField;
    private JTextField chickenField;
    private JTextField fishField;

    public Main() {
        this.setTitle("Carbon Footprint Calculator");
        this.setSize(500, 500);
        this.setDefaultCloseOperation(3);
        JPanel panel = new JPanel();
        this.add(panel);
        this.placeComponents(panel);
    }

    private void placeComponents(final JPanel panel) {
        panel.setLayout((LayoutManager)null);
        addLabel(panel, "Did you use any transportation today? (yes/no):", 10, 20);
        this.transportField = addTextField(panel, 310, 20);
        addLabel(panel, "Distance traveled (km):", 10, 60);
        this.distanceField = addTextField(panel, 310, 60);
        addLabel(panel, "Electricity used (kWh):", 10, 100);
        this.electricityField = addTextField(panel, 310, 100);
        addLabel(panel, "Beef consumed (kg):", 10, 140);
        this.beefField = addTextField(panel, 310, 140);
        addLabel(panel, "Pork consumed (kg):", 10, 180);
        this.porkField = addTextField(panel, 310, 180);
        addLabel(panel, "Chicken consumed (kg):", 10, 220);
        this.chickenField = addTextField(panel, 310, 220);
        addLabel(panel, "Fish consumed (kg):", 10, 260);
        this.fishField = addTextField(panel, 310, 260);
        JButton calculateButton = new JButton("Calculate");
        calculateButton.setBounds(10, 300, 160, 25);
        panel.add(calculateButton);
        calculateButton.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                double dailyCarbonFootprint = 0.0;
                String transportUsed = Main.this.transportField.getText().trim().toLowerCase();
                if ("yes".equalsIgnoreCase(transportUsed)) {
                    String transportType = JOptionPane.showInputDialog("Transport type (car, motorcycle, bus):").trim().toLowerCase();
                    double distance = Main.getValidatedDouble(Main.this.distanceField.getText(), "distance");
                    dailyCarbonFootprint += Main.calculateTransportationCarbonFootprint(transportType, distance);
                }

                double electricityUsed = Main.getValidatedDouble(Main.this.electricityField.getText(), "electricity");
                dailyCarbonFootprint += Main.calculateElectricityCarbonFootprint(electricityUsed);
                dailyCarbonFootprint += Main.getValidatedDouble(Main.this.beefField.getText(), "beef") * 27.0;
                dailyCarbonFootprint += Main.getValidatedDouble(Main.this.porkField.getText(), "pork") * 12.0;
                dailyCarbonFootprint += Main.getValidatedDouble(Main.this.chickenField.getText(), "chicken") * 6.9;
                dailyCarbonFootprint += Main.getValidatedDouble(Main.this.fishField.getText(), "fish") * 5.0;
                double yearlyFootprint = dailyCarbonFootprint * Main.getAnnualMultiplier();
                double totalCarbonFootprint = Main.loadData() + dailyCarbonFootprint;
                JOptionPane.showMessageDialog(panel, String.format("Total daily emissions: %.2f kg CO2%nEstimated yearly: %.2f kg CO2", dailyCarbonFootprint, yearlyFootprint));
                if (yearlyFootprint > 2000.0) {
                    Main.printWaysToReduceCarbonEmissions();
                } else {
                    JOptionPane.showMessageDialog(panel, "Your emissions are below average. Well done!");
                }

                Main.saveData(totalCarbonFootprint);
            }
        });
    }

    private static JLabel addLabel(JPanel panel, String text, int x, int y) {
        JLabel label = new JLabel(text);
        label.setBounds(x, y, 300, 25);
        panel.add(label);
        return label;
    }

    private static JTextField addTextField(JPanel panel, int x, int y) {
        JTextField textField = new JTextField(20);
        textField.setBounds(x, y, 160, 25);
        panel.add(textField);
        return textField;
    }

    private static double getValidatedDouble(String input, String fieldName) {
        while(true) {
            try {
                double value = Double.parseDouble(input);
                if (value >= 0.0) {
                    return value;
                }

                input = JOptionPane.showInputDialog(fieldName + " cannot be negative. Enter again:");
            } catch (NumberFormatException var4) {
                input = JOptionPane.showInputDialog("Enter a valid number for " + fieldName + ":");
            }
        }
    }

    private static double calculateTransportationCarbonFootprint(String transportType, double distance) {
        switch (transportType) {
            case "car":
                String carType = JOptionPane.showInputDialog("Car type (petrol sedan, diesel sedan, electric):").trim().toLowerCase();
                return calculateCarCarbonFootprint(carType, distance);
            case "motorcycle":
                return distance * 88.0 / 1000.0;
            case "bus":
                return distance * 104.0 / 1000.0;
            default:
                JOptionPane.showMessageDialog((Component)null, "Invalid transport type.");
                return 0.0;
        }
    }

    private static double calculateCarCarbonFootprint(String carType, double distance) {
        switch (carType) {
            case "petrol sedan":
                return distance * 143.0 / 1000.0;
            case "diesel sedan":
                return distance * 164.0 / 1000.0;
            case "electric":
                return distance * 0.0 / 1000.0;
            default:
                JOptionPane.showMessageDialog((Component)null, "Invalid car type.");
                return 0.0;
        }
    }

    private static double calculateElectricityCarbonFootprint(double electricityUsed) {
        return electricityUsed * 0.233;
    }

    private static double getAnnualMultiplier() {
        String estimateType = JOptionPane.showInputDialog("Estimate type (daily/monthly):").trim().toLowerCase();
        return "monthly".equals(estimateType) ? 12.0 : 365.0;
    }

    private static void printWaysToReduceCarbonEmissions() {
        JOptionPane.showMessageDialog((Component)null, "To reduce emissions:\n1. Use energy-efficient appliances.\n2. Opt for public transport or biking.\n3. Reduce meat consumption.");
    }

    private static double loadData() {
        File file = new File("carbon_footprint_data.txt");
        if (!file.exists()) {
            return 0.0;
        } else {
            try {
                BufferedReader reader = new BufferedReader(new FileReader(file));

                double var5;
                try {
                    double total = 0.0;

                    while(true) {
                        String line;
                        if ((line = reader.readLine()) == null) {
                            var5 = total;
                            break;
                        }

                        total += Double.parseDouble(line);
                    }
                } catch (Throwable var8) {
                    try {
                        reader.close();
                    } catch (Throwable var7) {
                        var8.addSuppressed(var7);
                    }

                    throw var8;
                }

                reader.close();
                return var5;
            } catch (NumberFormatException | IOException var9) {
                JOptionPane.showMessageDialog((Component)null, "Error loading data.");
                return 0.0;
            }
        }
    }

    private static void saveData(double totalCarbonFootprint) {
        try {
            BufferedWriter writer = new BufferedWriter(new FileWriter("carbon_footprint_data.txt", true));

            try {
                writer.write(String.valueOf(totalCarbonFootprint));
                writer.newLine();
            } catch (Throwable var6) {
                try {
                    writer.close();
                } catch (Throwable var5) {
                    var6.addSuppressed(var5);
                }

                throw var6;
            }

            writer.close();
        } catch (IOException var7) {
            JOptionPane.showMessageDialog((Component)null, "Error saving data.");
        }

    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            Main frame = new Main();
            frame.setVisible(true);
        });
    }
}


                                                     

                                                


