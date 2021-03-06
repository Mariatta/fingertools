================================
Boston Python miscellaneous code
================================

These are small programs I've used to help run Boston Python.

pizza.py calculates how much pizza to order.

attendees.py uses meetup.py to access the Meetup API to find out about RSVPs
to events.  My most famous use of this is to raffle prizes at events::

    $ python2.7
    >>> event_id = "234430898"  # From the meetup.com url for the event
    >>> from attendees import yes
    >>> people = yes(event_id)
    opening 'https://api.meetup.com/2/rsvps?event_id=234430898&key=xyzzy'
    >>> len(people)
    105
    >>> import random
    >>> random.shuffle(people)
    >>> winners = iter(people)
    >>> print(next(winners))
    Gabriel Morell
    >>> print(next(winners))
    Amr Elhagary
    >>> print(next(winners))
    Oscar Arevalo-Toledo
    >>> print(next(winners))
    Albert Putnam

To run this, you'll need to create a keys.py file, with the API key you get
from the `Meetup API`_ page::

    API_KEY = "93d17c424e4f535877437b5a3a4150"

.. _Meetup API: https://secure.meetup.com/meetup_api/key/
