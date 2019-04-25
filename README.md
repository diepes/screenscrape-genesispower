# screenscrape-genesispower
Screen scrape daily electricity use from genesis website

#Pieter Notes
1. python3 -m venv venv
2. . ./venv/bin/activate
3. pip install requests BeautifulSoup4

Test interactive in python
1. python
>>> from getPwrFrmGenesis import simple_get
>>> raw_html = simple_get('https://myaccount.genesisenergy.co.nz/auth/login')
>>> len(raw_html)
5147

HTTPS debug / tracing
https://auth-api.genesisenergy.co.nz/v1/token 
    (Request Headers Authorization: Basic xxbase64??xx )
    (Form Data,  grant_type=password&username=name@email.com&password=xxxxxx )
    (Response: {"access_token":"423b6da1ab712f5a0a2f582fc91aa57a20bedc7e","token_type":"bearer","expires_in":3539,"refresh_token":"2e19f4147d23cbc81a1354f2d87a892028e1616e"} )
https://web-api.genesisenergy.co.nz/v2/private/billing/accounts
    (Request Headers Authorization: Bearer 423b6da1ab712f4a0a2f482fc91aa57a20bedc7e )
https://web-api.genesisenergy.co.nz/v2/private/billing/service
https://web-api.genesisenergy.co.nz/v2/private/dashboard
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/authenticate?billingNum=<<retrieved_before>>>
    ( response   token, permissions etc.)
https://web-api.genesisenergy.co.nz/v2/private/flybuys
https://web-api.genesisenergy.co.nz/v2/private/user/metadata
https://web-api.genesisenergy.co.nz/v2/private/bootstrap
https://web-api.genesisenergy.co.nz/v2/private/electricity/billPeriod
    (YES contains all the details kw, $ pre day)
https://web-api.genesisenergy.co.nz/v2/private/billing/summary
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/forecasts
   (Request Haders: Authorization: Bearer )
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/home-profile
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/thirty-day-insights  
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/latest-insights
https://ecosystem-exp-api.genesisenergy.co.nz/eiq/v1/insights?year=2019

Check consumption
https://web-api.genesisenergy.co.nz/v2/private/electricity/usage
https://web-api.genesisenergy.co.nz/v2/private/electricity/usage
   (Request Payload: {"limit":100,"caching":true,"startDate":"2019-04-13","endDate":"2019-04-13","intervalType":"HOURLY"} )





