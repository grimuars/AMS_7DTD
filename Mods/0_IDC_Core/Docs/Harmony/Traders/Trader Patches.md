# Trader Patches
IDC Core features Harmony patches that enable each trader to use a separate currency. To make use of this feature, a trader must be given a specific currency different than the global currency to use. There are multiple ways to specify the currency for a trader. 

The first method is to modify `traders.xml` manually and add the `currency_item` attribute to the traders corresponding `trader_info` entry.
`<trader_info id="6" reset_interval="3" open_time="6:05" close_time="21:50" currency_item="<item name>">`

The second and ideal way is to use xpath to add the attribute to the trader's `trader_info` entry.
`<setattribute xpath="traders/trader_info[@id='<trader id>']" name="currency_item"><item name></setattribute>`
