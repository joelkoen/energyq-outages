# energyq-outages

Outage history for Ergon and Energex in Queensland, Australia.

Every five minutes, this repository is updated with data from the following URLs:

- https://www.ergon.com.au/static/Ergon/ergon_po_current_unplanned.geojson
- https://www.ergon.com.au/static/Ergon/ergon_po_current_planned.geojson
- https://www.ergon.com.au/static/Ergon/ergon_po_future_planned.geojson
- https://www.energex.com.au/static/Energex/energex_po_current_unplanned.geojson
- https://www.energex.com.au/static/Energex/energex_po_current_planned.geojson
- https://www.energex.com.au/static/Energex/energex_po_future_planned.geojson

To make it easier to track changes using Git, the data is formatted and sorted using jq:

```sh
jq '.features|=sort_by(.properties.EVENT_ID)'
```
