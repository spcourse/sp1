# Lists

A list in Python is a useful way of grouping data so they can be interacted with as a whole. This way calculations can be performed on the entire collection in one go instead of each number individually.

## Video

![embed](https://api.eu.kaltura.com/p/120/sp/12000/embedIframeJs/uiconf_id/23449960/partner_id/120?iframeembed=true&playerId=kaltura_player&entry_id=0_nlkxjtml&flashvars[streamerType]=auto&amp;flashvars[localizationCode]=en_US&amp;flashvars[leadWithHTML5]=true&amp;flashvars[sideBarContainer.plugin]=true&amp;flashvars[sideBarContainer.position]=left&amp;flashvars[sideBarContainer.clickToClose]=true&amp;flashvars[chapters.plugin]=true&amp;flashvars[chapters.layout]=vertical&amp;flashvars[chapters.thumbnailRotator]=false&amp;flashvars[streamSelector.plugin]=true&amp;flashvars[EmbedPlayer.SpinnerTarget]=videoHolder&amp;flashvars[dualScreen.plugin]=true&amp;flashvars[hotspots.plugin]=1&amp;flashvars[Kaltura.addCrossoriginToIframe]=true&amp;&wid=0_r1d1hzq5)

## Reference

The following code creates a new list called `staff` filled with strings (names):

    staff = ["Martijn", "Ivo", "Jelle", "Maarten", "Huub", "Marianne"]

You can request a single element of a list with `[`, `]`. The following code prints "Jelle"

    my_name = staff[2]
	print(my_name)

Beware that you start counting at `0` with indexing lists. So the following code prints "Martijn":

    my_name = staff[0]
	print(my_name)

You can also manipulate the content of a list. The following code changes the 3d element of the list.

    staff[3] = "Vera"

So now the list `staff` is: `["Martijn", "Ivo", "Jelle", "Vera", "Huub", "Marianne"]`

You can add an element to the end of the list (i.e, extending it):

    staff.append("Tom")

You can loop through the elements of a list using `for`:

    measurements_science_park = [12.7, 18.8, 24.9, 14.5, 19.0]
    measurements_science_park.append(20.5)
    for measurement in measurements_science_park:
        print(f"the measurement was {measurement} degrees.")

## For more details:

In English, read about [lists](http://greenteapress.com/thinkpython/html/thinkpython011.html) at Think Python.
