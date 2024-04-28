## Setup monitoring using Prometheus and Grafana for jenkins

### Prerequisites

- Prometheus server needs to be running
- Grafana server needs to be running

### Step 1: Install Prometheus Plugin

1. Go to Jenkins Dashboard
2. Click on `Manage Jenkins`
3. Click on `Manage Plugins`
4. Click on `Available` tab
5. Search for `Prometheus Metrics Plugin`
6. Click on `Install without restart`
7. Safe Restart Jenkins
8. Prometheus plugin adds the /prometheus endpoint to Jenkins
9. Prometheus plugin exposes the metrics in the Prometheus format

### Step 2: Update the Prometheus Configuration

1. Go to Prometheus configuration file
2. Add the following configuration to the file

```yaml
- job_name: "jenkins"
  metrics_path: "/prometheus"
  static_configs:
    - targets: ["<Jenkins host name>:8080"]
```

3. Restart the Prometheus server
4. Prometheus will start scraping the Jenkins metrics
5. Verify the status of the Jenkins metrics in Prometheus
6. Go to Prometheus Dashboard
7. Search for `jenkins` in the search bar

### Step 3: Update grafana datasources

1. Go to Grafana Dashboard
2. Click on `Configuration`
3. Click on `Data Sources`
4. Click on `Add data source`
5. Select `Prometheus` as the data source
6. Add the URL of the Prometheus server
7. Click on `Save & Test`

### Step 4: Import Jenkins Dashboard

1. Go to Grafana Dashboard
2. Click on `Create`
3. Click on `Import`
4. Enter the Jenkins Dashboard ID `1860`
5. Click on `Load`
6. Select the Prometheus data source
7. Click on `Import`
