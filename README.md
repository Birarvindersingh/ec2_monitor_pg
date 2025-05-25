<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
</head>
<body>

  <h1>📈 Monitoring Project: Prometheus + Grafana on EC2</h1>

  <p>This project demonstrates how to monitor an AWS EC2 instance and a sample backend using <strong>Prometheus</strong> and <strong>Grafana</strong>. It covers metric collection, dashboard visualization, and optional alert rules, giving a beginner-friendly introduction to observability in DevOps.</p>

  <h2>📦 Project Overview</h2>
  <ul>
    <li>Launch an Ubuntu EC2 instance on AWS</li>
    <li>Install and run <code>node_exporter</code> to collect system metrics</li>
    <li>Install Prometheus and configure it to scrape metrics from <code>node_exporter</code></li>
    <li>Install and set up Grafana to visualize Prometheus data</li>
    <li>Import a prebuilt Node Exporter dashboard in Grafana</li>
    <li>Set up alert rules in <code>prometheus.yml</code></li>
  </ul>

  <h2>🛠️ Technologies Used</h2>
  <ul>
    <li>Prometheus</li>
    <li>Grafana</li>
    <li>Node Exporter</li>
    <li>AWS EC2 (Ubuntu)</li>
  </ul>

  <h2>🔔 Optional Alert Rule</h2>
  <pre><code>groups:
  - name: alert_rules
    rules:
    - alert: HighCPUUsage
      expr: 100 - (avg by(instance) (rate(node_cpu_seconds_total{mode="idle"}[2m])) * 100) > 80
      for: 2m
      labels:
        severity: warning
      annotations:
        summary: "High CPU usage detected on {{ $labels.instance }}"
        description: "CPU usage is above 80% for more than 2 minutes."
</code></pre>

  <h2>📸 Project Screenshots</h2>
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/1.PNG" alt="Screenshot 1" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/2.PNG" alt="Screenshot 2" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/3.PNG" alt="Screenshot 3" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/4.PNG" alt="Screenshot 4" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/5.PNG" alt="Screenshot 5" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/6.PNG" alt="Screenshot 6" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/7.PNG" alt="Screenshot 7" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/8.PNG" alt="Screenshot 8" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/9.PNG" alt="Screenshot 9" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/10.PNG" alt="Screenshot 10" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/11.PNG" alt="Screenshot 11" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/12.PNG" alt="Screenshot 12" width="500" />
  <img src="https://github.com/Birarvindersingh/ec2_monitor_pg/blob/main/13.PNG" alt="Screenshot 13" width="500" />

  <h2>✅ Conclusion</h2>
  <p>This beginner-friendly monitoring setup helped me understand how to collect, visualize, and optionally alert on infrastructure metrics. Observability is a core skill for DevOps, and this project gave me hands-on experience with Prometheus and Grafana.</p>

</body>
</html>
