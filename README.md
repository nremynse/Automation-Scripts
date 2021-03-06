# Automation-Scripts
Random scripts to automate various things.


## censys_monitor.py
Used to monitor censys.io API for newly created SSL certs that match a specific pattern. Using it as an early detection for new phishing domains. Quite successful so far :).<br>
Example usage in cron: `0 */3 * * * /opt/censys/venv/bin/python /opt/censys/censys_monitor.py`
    
## viper_monitor.py
Monitors directory and uploads any file that's placed there to the [Viper Framework](https://github.com/viper-framework/viper). Also checks Virus Total for matches with an API key.

## dynamic_cloudflare.py
Updates cloudflare with your IP. Helpful if you don't have anything else to update it and are on a dynamic IP from your ISP.<br>
Example usage in cron: `*/5 * * * * /opt/Cloudflare_Scripts/dynamicDNS.py dyn.domain.tech`

## reverseit_monitor.py
Monitors Hybrid Analysis [feed](https://www.hybrid-analysis.com/feed?json) for uploaded items. Won't catch it all but gets a good sampling. Handy for some fun stats / monitoring in elastic.

## ip_block.py
Monitors kafka for IPs to block. Blocks IP and reports it as an indicator to MISP.

## censys_monitor.py
Monitors censys for new cert registrations. Can use multiple api keys and works best with below cronjob.<br>
`0 */3 * * * /opt/censys/venv/bin/python /opt/censys/censys_monitor.py`

## dynamicDNS.py
Monitors public IP and reports that to cloudflare to update the IP there. 
`*/5 * * * * /opt/Cloudflare_Scripts/dynamicDNS.py dyn.remynse.tech`
