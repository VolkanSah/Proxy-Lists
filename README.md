
# Auto Proxy Fetcher

A tool for automatically fetching proxy servers and updating `proxies.txt` using GitHub Actions. You can either use my existing proxy list or set up your own version of this repository.

## Using the Proxy List

You can directly use the proxy list generated by this tool for your own programs, scripts, or applications. The proxy list is updated every 6 hours and is accessible via this URL:

```bash
https://raw.githubusercontent.com/VolkanSah/Auto-Proxy-Fetcher/refs/heads/main/proxies.txt
```

### Example Usage

You can use `curl` to download the proxy list directly:

```bash
curl https://raw.githubusercontent.com/VolkanSah/Auto-Proxy-Fetcher/refs/heads/main/proxies.txt -o proxies.txt
```

Or, you can integrate it into a Python script:

```python
import requests

url = "https://raw.githubusercontent.com/VolkanSah/Auto-Proxy-Fetcher/refs/heads/main/proxies.txt"
response = requests.get(url)

if response.status_code == 200:
    with open('proxies.txt', 'w') as f:
        f.write(response.text)
else:
    print(f"Failed to fetch proxies: {response.status_code}")
```

## Why Every 6 Hours?

Proxies, especially reliable ones, don't change frequently. Therefore, fetching proxies every 6 hours is optimal because:

- **Stability:** Trusted proxy sources update less frequently.
- **Efficient Use of Resources:** By fetching every 6 hours, GitHub Actions minutes are conserved.
- **Rate Limiting Prevention:** Regular fetching avoids triggering rate limits on the proxy sources.
- **Server Load:** It helps reduce the load on the proxy provider servers, ensuring better service for all users.

## How to Set Up Your Own Version

If you want to use this tool on your own GitHub account and customize the workflow, follow these steps:

1. **Fork the Repository:**
   - Go to the [Auto Proxy Fetcher Repository](https://github.com/VolkanSah/Auto-Proxy-Fetcher).
   - Click on the "Fork" button to create a copy on your own GitHub account.

2. **Set Up GitHub Actions Workflow:**
   - In your forked repository, go to the "Actions" tab.
   - The workflow should be automatically enabled.
   - You can manually start it by clicking the "Run workflow" button.

3. **Automatic Updates:**
   - The workflow will automatically run every 6 hours.
   - It will update `proxies.txt` with the latest proxy list and commit it to your repository.

By following these steps, you'll have your own proxy fetching tool running on GitHub Actions with customized settings.

Your support is greatly appreciated. If you find MiniGreX CMS useful, consider ⭐ the project on GitHub or becoming a [Sponsor](https://github.com/sponsors/volkansah).

### copyright 
**S. Volkan Kücükbudak**
