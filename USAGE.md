<!-- Start SDK Example Usage -->
```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    api_key="<YOUR_API_KEY>",
)


res = s.menu.drinks.list()

if res.classes is not None:
    # handle response
    pass
```
<!-- End SDK Example Usage -->