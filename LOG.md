# Debug log

Your notes. One entry per bug you fixed, using the template below.

This file is read as carefully as your code. A correct fix you cannot
explain counts for little; a bug you could not fix but investigated
honestly still counts for something.

Delete the example before you submit.



## Example — delete this

### CC-99 — "The cart total is wrong"

**Reproduced:** Added 2 dosas at Rs. 60 each. The cart showed
Rs. 119.99999 instead of Rs. 130. Happened every time, on any dish with
a price ending in .50.

**Cause:** The total was being added up with plain floating point and
never rounded, so 0.1 + 0.2 style errors showed up on screen. The
rounding helper existed but this one place was not using it.

**Fix:** Ran the total through the existing rounding helper instead of
adding a new one, so every price on screen goes through the same path.

**Checked:** Cart, checkout and the order screen all show Rs. 130 now.
Prices without decimals still show without a trailing .00.

**Time:** about 40 minutes, most of it working out that the cart and the
order screen round in different places.



## CC-0X — "<the complaint, in short>"

**Reproduced:**

**Cause:**

**Fix:**

**Checked:**

**Time:**



## Could not fix

For anything you investigated but did not solve. Say what you tried and
where you got to. This is worth marks — leaving it blank when you got
stuck is not.

### CC-0X — "<the complaint>"

**What I tried:**

**Where I got to:**

**What I would try next:**



## Extra credit

Anything not on the bug log: a problem you found yourself, a test you
wrote, or a fix you are unsure about. Same format, plus one line on how
you noticed it.



### CC-02: "Can't read anything in dark mode"

**Reproduced:**
- Opened the site on localhost
- Clicked dark mode toggle
- Food name and price of the food are not visible clearly

**Cause:**
- Opened DevTools using F12
- Went to the Elements tab and inspected the dish name/price
- Found they belong to class `.dish-body`, and in dark mode this class's text color isn't changing — stays same as light mode

**Fix:**
- In dark mode, set `.dish-body` text color to white (or light color) so it's visible against dark background
- Left light mode styling untouched — it was already correct.

