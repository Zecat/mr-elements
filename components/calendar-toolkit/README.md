# calendar-toolkit

The idyllic idea of this set of tools is to handle the complexity of generating a calendar, associate data to the dates and add selectable features (simple, interval or multiple discontinuous) to an existing calendar simply by extending behaviors.

The code may sound very obscure as not documented and there's still a lot of work to do but give it a try!

- `calendar-generation-behavior` handle the calendar generation.
- `calendar-multi-selectable-behavior` allows multiple and discontinuous selection of dates in a theoretically infinit calendar.
- `calendar-interval-selectable-behavior` allows the selection of one continuous interval.
- `calendar-properties-toggling-behavior` helps to manipulate the boolean properties associated to the dates (as the selected state).
- `date-selection-behavior` observes the user input (mouse or touch events) to know the dates he want to select. You'll need to override '_getDateFromTarget'.

## demo & doc

See [component page](http://zecat.github.io/calendar-toolkit)
