
```
import simplejson, urllib2, urllib

def get_inlink_data(appid, query, results=50, start=1, entire_site="", omit_inlinks=""):
    """>>> get_inlink_data('YahooDemo', u'http://reddit.com')
    """
    base_url = u'http://search.yahooapis.com/SiteExplorerService/V1/inlinkData?'
    params = locals()
    result = _query_yahoo(base_url, params)
    return result['ResultSet']['Result']

def get_page_data(appid, query, results=50, start=1, domain_only = ""):
    """>>> get_page_data('YahooDemo', u'http://reddit.com')
    """
    base_url = u'http://search.yahooapis.com/SiteExplorerService/V1/pageData?'
    params = locals()
    result = _query_yahoo(base_url, params)
    return result['ResultSet']['Result']

def do_ping(sitemap):
    """>>> do_ping(u'http://www.google.com/sitemap.xml')
    """
    base_url = u'http://search.yahooapis.com/SiteExplorerService/V1/ping?'
    params = locals()
    return _query_yahoo(base_url, params)

def do_update_notification(appid, url):
    """>>> do_update_notification('YahooDemo', 'http://www.google.com/')
    """
    base_url = u'http://search.yahooapis.com/SiteExplorerService/V1/updateNotification?'
    params = locals()
    return _query_yahoo(base_url, params)

def _query_yahoo(base_url, params):
    params['output'] = 'json'
    payload = urllib.urlencode(params)
    url = base_url + payload
    response = urllib2.urlopen(url)
    result = simplejson.load(response)
    return result    

```