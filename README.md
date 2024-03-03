# CryptoTracker

CryptoTracker is an open-source project designed to simplify the collection, storage, analysis, visualization, and monitoring of cryptocurrency data. Whether you're a developer, researcher, or trader, CryptoTracker provides a robust platform to explore and understand cryptocurrency markets across major exchanges.

## Features

- **Data Tracking:** Track cryptocurrency prices, bid/ask spreads, size, and volume.
- **Research and Analysis:** Test market hypotheses, build machine learning models, and explore price movements.
- **Visualization:** Utilize powerful visualizations and dashboards in Kibana for comprehensive market insights.
- **Exchange Support:** CryptoTracker supports major exchanges, including BitFinex, BitTrex, Bitmex, GDAX, Gemini, Kraken, OKCoin, Poloniex, and BitMex.

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/)

### Running CryptoTracker

1. Clone this repository.

   ```bash
   git clone https://github.com/your-username/CryptoTracker.git
   ```

2. Navigate to the project directory.

   ```bash
   cd CryptoTracker
   ```

3. Build and launch the Docker containers.

   ```bash
   docker-compose build && docker-compose up
   ```

4. Access Kibana at [http://localhost:5601/](http://localhost:5601/) once the system loads (may take a few minutes).

### Optional Configuration

- Adjust timer settings in `settings.py`.
- Configure log verbosity in `default.env`.

### Setting Up Index Patterns in Kibana

1. Add the following index patterns in Kibana with the Time-field name set to `tracker_time`:
   - `eth.*.ticker`
   - `btc.*.ticker`
   - `*.*.ticker`

2. Import saved objects and dashboards from the provided JSON file under `/resources` through Kibana's UI (Management -> Saved Objects -> Import).

### Production Settings

For live systems, set `vm_map_max_count` permanently in `/etc/sysctl.conf`:

```bash
$ grep vm.max_map_count /etc/sysctl.conf
vm.max_map_count=262144
```

### Additional Resources

- In a development environment, a Kibana configuration script (`resources/configure-kibana.sh`) is provided for automatic setup. Note that it's not recommended for production due to occasional issues with the discover tab after import.

## Contributing

Pull requests are welcome! Feel free to contribute to the development and improvement of CryptoTracker.


## Acknowledgments

Thank you to all contributors who help make CryptoTracker a powerful tool for cryptocurrency research and development. Your contributions are highly appreciated!
