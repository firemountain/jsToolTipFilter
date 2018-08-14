# jsToolTipFilter

## project description 

we want to display the content from an iframe widget within a pre-exiting javascript controled image map tooltip script.

you can see the example of the image map tool tip script (the map with the colored shapes on it) and the iframe widget (the real estate listings) here:

http://104.236.52.68/

as you can see, within the tooltip content of each tooltip are some json values,

we want to use those json values to fetch the html content displayed on the screen within the iframe widget, filter it(using the specific values for each tooltip), and display it witin each tool tip containing json values. 


## project goals

- use the json values within each "tooltip-content" to filter the content from the appfolio widget(iframe on the page) and copy it into each tooltip
- use an overlay and "loading" spinner to hide the page content from the user until the the page with the iframe data loads, then write html copied from the iframe and replace the "tooltip_content" in the image map script (the image map script is in the repo)

the tool tip containing :
`
{"id":"rect-4176","title":"rect-4176","type":"poly","x":34.335,"y":26.025,"width":19.198,"height":14.992,"default_style":{"fill":"#00ff00","stroke_color":"#408000","stroke_width":3},"mouseover_style":{"fill":"#ffcc66"},"tooltip_style":{"background_color":"#ffffff"},"tooltip_content":{"plain_text":"{name:"Mid Century Creative Studio - Bishop Arts District - Outdoor Garden",rent-max:4000,rent-min:2000,sqft-max:2000,sqft-min:2000}","plain_text_color":"#000000"},"points":[{"x":1.098901098901099,"y":94.5945945945946},{"x":7.142857142857142,"y":82.88288288288288},{"x":0,"y":82.88288288288288},{"x":20.87912087912088,"y":50.45045045045045},{"x":29.120879120879124,"y":50.45045045045045},{"x":35.714285714285715,"y":41.44144144144144},{"x":32.967032967032964,"y":39.63963963963964},{"x":40.65934065934066,"y":27.927927927927925},{"x":46.15384615384615,"y":27.927927927927925}
`

contains: 

`"tooltip_content":{"plain_text":"{name:"Mid Century Creative Studio - Bishop Arts District - Outdoor Garden",rent-max:4000,rent-min:2000,sqft-max:2000,sqft-min:2000}"`

we want to use :

`{name:"Mid Century Creative Studio - Bishop Arts District - Outdoor Garden",rent-max:4000,rent-min:2000,sqft-max:2000,sqft-min:2000}`

to check against the data being displayed in the appfolio widget:

so in this example, the result would be as below, because the listing on the appfolio widget matches the json filters in the tool tip text, i.e. the display Name "Mid Century Creative Studio - Bishop Arts District - Outdoor Garden" on the appfolio widget matches the name: value in the json, and the values for Rent and Square Feet in the appfolio widget fall within the range defined in the JSON. 

![alt text](http://104.236.52.68/images/example.jpg "example")

note that the first listing on the appfolio widget does not appear in the tool tip because although the display Name from the widget matches, the Rent and Square Feet do not fit within the range defined by rent-max, rent-min, and sqft-max, sqft-min in the json.

### another example 

for :

`{"id":"rect-7894","title":"rect-7894","type":"poly","x":8.07,"y":67.354,"width":19.726,"height":10.94,"default_style":{"fill":"#ffcc66","stroke_color":"#ff0000","stroke_width":3},"mouseover_style":{"fill":"#00ff00"},"tooltip_style":{"background_color":"#ffffff"},"tooltip_content":{"plain_text":"{name:"Mid Century Creative Studio - Bishop Arts District - Outdoor Garden"}","plain_text_color":"#000000"},"points":[{"x":0,"y":99.38271604938271},{"x":2.941176470588235,"y":90.12345679012346},{"x":8.02139037433155,"y":90.74074074074075},{"x":34.49197860962567,"y":29.629629629629626},{"x":64.43850267379679,"y":3.0864197530864197},{"x":64.70588235294117,"y":9.876543209876543},{"x":71.12299465240642,"y":9.876543209876543},{"x":75.1336898395722,"y":1.2345679012345678},{"x":98.1283422459893,"y":0},{"x":97.86096256684492,"y":7.4074074074074066},{"x":97.59358288770053,"y":12.962962962962962},{"x":97.59358288770053,"y":17.901234567901234},{"x":97.59358288770053,"y":28.39506172839506},{"x":98.93048128342245,"y":30.864197530864196},{"x":100,"y":36.41975308641975},{"x":97.05882352941177,"y":42.592592592592595},{"x":91.17647058823529,"y":39.50617283950617},{"x":76.20320855614973,"y":77.77777777777779},{"x":81.81818181818183,"y":79.01234567901234},{"x":71.65775401069519,"y":97.53086419753086},{"x":70.05347593582889,"y":100},{"x":45.18716577540107,"y":98.76543209876543},{"x":43.58288770053476,"y":95.67901234567901},{"x":47.593582887700535,"y":87.65432098765432},{"x":18.181818181818183,"y":83.9506172839506},{"x":11.76470588235294,"y":99.38271604938271}]},`

the only value in the json is {name:"Mid Century Creative Studio - Bishop Arts District - Outdoor Garden"}

of the 3 listings in the appfolio widget, all have the same name, 

so on the tooltip content for this tooltip, all 3 listings would show as a scrollable list within the tooltip












