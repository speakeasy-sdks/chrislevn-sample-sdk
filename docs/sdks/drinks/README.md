# Drinks
(*menu.drinks*)

### Available Operations

* [list](#list) - Get a list of drinks

## list

Get a list of drinks

### Example Usage

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


### Response

**[operations.ListDrinksV2GetResponse](../../models/operations/listdrinksv2getresponse.md)**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 4x-5xx          | */*             |
