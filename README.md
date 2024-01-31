# Admin Dashboard

---

## Admin Dashboard

**Note:** Updated information will be displayed below.

---

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Dashboard</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }

        #admin-dashboard {
            border: 1px solid #ccc;
            padding: 10px;
            margin-top: 20px;
        }

        #admin-dashboard p {
            margin: 5px 0;
        }
    </style>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Open a connection to the SSE endpoint
            const eventSource = new EventSource('https://pvaaaaaaaa.github.io/Panic-Server//sse');

            // Listen for messages from the server
            eventSource.onmessage = function(event) {
                const message = JSON.parse(event.data);
                // Handle the received message (e.g., update the dashboard)
                console.log('Received message:', message);
                // Update the admin dashboard with the received information
                updateDashboard(message);
            };

            // Handle SSE errors
            eventSource.onerror = function(error) {
                console.error('Error with SSE:', error);
            };
        });

        // Function to update the admin dashboard with received information
        function updateDashboard(message) {
            const dashboardElement = document.getElementById('admin-dashboard');
            const newMessageElement = document.createElement('p');
            newMessageElement.textContent = message;
            dashboardElement.appendChild(newMessageElement);
        }
    </script>
</head>
<body>
    <h1>Admin Dashboard</h1>
    <div id="admin-dashboard">
        <!-- Updated information will be displayed here -->
    </div>
</body>
</html>

