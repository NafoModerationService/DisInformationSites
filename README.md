# DisInformation Sites
## Evaluation process
Every site in all list are evaluated, IF they are not marked for deletion. 
- A http call will be done to the site.
- If it is clearly removed, it will be marked for deletion. 
- If it returns 200 OK, it will be marked active.
- If not, the user will be presented with the result, and asked if it is "Active or Not".

### Status: 
Follows http errorcodes or "just something I made up"
```
public enum enumStatus {
    unknown_status              = 0,
    http_siteActive             = 1,       // 200 OK
    http_redirect               = 302,
    http_movedPermanently       = 321,
    http_badRequest             = 400,
    http_forbidden              = 403,
    http_pageNotFound           = 404,
    http_tooManyRequests        = 429,
    http_unknown_host           = 521,

    site_sslError               = 11,        // SSL certificate error. The SSL connection could not be established, see inner exception.

    netTimeout                  = 21,        // Can also mean Site is down
    netUnknownHost              = 22,        // No DNS entry / No such host is known.
    netNoHostRecordInDomain     = 23,        // No host entry in domain
    netNoHostActivlyRefused     = 24
}
```

## Template record
```
{
  "Name": "Disinformation websites Russia",
  "Description": "Wikipedia list.",
  "Reference": "https://en.wikipedia.org/wiki/List_of_political_disinformation_website_campaigns_in_Russia",

  "Sites": [
    {
      "name": "",
      "deleted": true,
      "active": true,
      "url": "",
      "notes": "",
      "status": 22
    }
  ]
}
```
### Heading
- Name : Name of the list
- Description: Details
- Reference: If any, link to source list
- Array of sites

### Sites
- Name: If any, if not empty or url
- deleted: Removed from evaluation, typically defunked or no DNS entry. 
- active: Site is active
