
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CPU Scheduling Simulator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f0f0f0;
        }

        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        .input-section {
            margin-bottom: 20px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }

        th {
            background-color: #4CAF50;
            color: white;
        }

        input[type="number"], input[type="text"] {
            width: 100%;
            padding: 5px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        .gantt-chart {
            display: flex;
            margin-top: 20px;
            padding: 10px;
            background-color: white;
        }

        .gantt-block {
            padding: 5px 10px;
            border: 1px solid #333;
            margin-right: 2px;
            background-color: #4CAF50;
            color: white;
        }

        .metrics {
            margin-top: 20px;
            padding: 10px;
            background-color: #e8f5e9;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>CPU Scheduling Simulator (FCFS)</h2>
        
        <div class="input-section">
            <label>Number of Processes:</label>
            <input type="number" id="processCount" min="1" value="3">
            <button onclick="createProcessTable()">Generate Table</button>
        </div>

        <table id="processTable">
            <thead>
                <tr>
                    <th>Process ID</th>
                    <th>Arrival Time</th>
                    <th>Burst Time</th>
                    <th>Waiting Time</th>
                    <th>Turnaround Time</th>
                </tr>
            </thead>
            <tbody id="tableBody"></tbody>
        </table>

        <button onclick="calculateFCFS()">Calculate</button>

        <div class="metrics" id="metrics"></div>
        <div class="gantt-chart" id="ganttChart"></div>
    </div>

    <script>
        function createProcessTable() {
            const count = parseInt(document.getElementById('processCount').value);
            const tbody = document.getElementById('tableBody');
            tbody.innerHTML = '';

            for(let i = 0; i < count; i++) {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td><input type="text" value="P${i+1}"></td>
                    <td><input type="number" value="${i}"></td>
                    <td><input type="number" value="${Math.floor(Math.random() * 5 + 1)}"></td>
                    <td></td>
                    <td></td>
                `;
                tbody.appendChild(row);
            }
        }

        function calculateFCFS() {
            const rows = document.querySelectorAll('#tableBody tr');
            const processes = [];

            // Collect process data
            rows.forEach((row, index) => {
                const cells = row.querySelectorAll('input');
                processes.push({
                    pid: cells[0].value,
                    arrival: parseInt(cells[1].value),
                    burst: parseInt(cells[2].value),
                    index: index
                });
            });

            // Sort processes by arrival time
            processes.sort((a, b) => a.arrival - b.arrival);

            let currentTime = 0;
            let totalWaiting = 0;
            let totalTurnaround = 0;
            const gantt = [];

            processes.forEach(process => {
                if(currentTime < process.arrival) {
                    gantt.push({
                        type: 'idle',
                        start: currentTime,
                        end: process.arrival
                    });
                    currentTime = process.arrival;
                }

                const start = currentTime;
                const end = currentTime + process.burst;
                const waiting = start - process.arrival;
                const turnaround = end - process.arrival;

                gantt.push({
                    type: 'process',
                    pid: process.pid,
                    start: start,
                    end: end
                });

                // Update table
                const row = rows[process.index];
                row.children[3].textContent = waiting;
                row.children[4].textContent = turnaround;

                totalWaiting += waiting;
                totalTurnaround += turnaround;
                currentTime = end;
            });

            // Update metrics
            const avgWaiting = totalWaiting / processes.length;
            const avgTurnaround = totalTurnaround / processes.length;
            document.getElementById('metrics').innerHTML = `
                <h3>Performance Metrics:</h3>
                <p>Average Waiting Time: ${avgWaiting.toFixed(2)}</p>
                <p>Average Turnaround Time: ${avgTurnaround.toFixed(2)}</p>
            `;

            // Draw Gantt chart
            const ganttDiv = document.getElementById('ganttChart');
            ganttDiv.innerHTML = '';
            gantt.forEach(block => {
                const div = document.createElement('div');
                div.className = 'gantt-block';
                div.style.width = `${(block.end - block.start) * 40}px`;
                div.innerHTML = `
                    ${block.type === 'idle' ? 'Idle' : block.pid}<br>
                    ${block.start}-${block.end}
                `;
                ganttDiv.appendChild(div);
            });
        }

        // Create initial table
        createProcessTable();
    </script>
</body>
</html>
