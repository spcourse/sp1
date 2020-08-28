# Lists

A list in Python is a useful way of grouping data so they can be interacted with as a whole. This way calculations can be performed on the entire collection in one go instead of each number individually.

This video, in Dutch, explains some of a lists simple applications.

![embed](https://player.vimeo.com/video/287247201)

In English, read about [lists](http://greenteapress.com/thinkpython/html/thinkpython011.html) at Think Python.

## Reference

Creating a new list:

    staff = ["Martijn", "Ivo", "Jelle", "Maarten", "Huub", "Marianne"]

Requesting a single element:

    staff[2] # gives "Jelle", not "Ivo"!

Manipulating a single element:

    staff[3] = "Vera"

Adding an element to the end of a list:

    staff.append("Tom")

Loop through a list:

    measurements_science_park = [12.7, 18.8, 24.9, 14.5, 19.0]
    measurements_science_park.append(20.5)
    for measurement in measurements_science_park:
        print(f"the measurement was {measurement} degrees.")
