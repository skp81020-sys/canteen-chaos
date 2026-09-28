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
- change the hard coded value to the variblr 
-  Replaced color: #2b2118 with color: var(--ink).

**Checked:** 
    - verified the harmode and ligh mode in the prices and name 

**Time:**

  - 20 -25 All (.dash-class - 5min code red karne me kaha kaha hai sab : 10 min )


### CC-05: "The category bar scrolls away on my phone"

**Reproduced:**
Mobile view mein menu ko scroll karne par category/filter bar gayab ho ja raha tha.

**Cause:**
Category/filter bar mein sticky positioning use nahi ki gayi thi.

**Fix:**
Mobile view ke liye category/filter bar mein sticky positioning add kar di.
- .wrap { position: sticky;
  top: 0;
  z-index: 1000;
}

**Checked:**
Mobile viewport par menu ko scroll karke check kiya aur verify kiya ki category/filter bar ab visible rehta hai.

**Time:** 15min
 
### CC-01 : "The search suggestions are behind everything"

**Reproduced:**
Search box mein kuch type karne par search suggestions doosre elements ke peeche chali ja rahi thi.

**Cause:**
`.search-wrap` ka `z-index` sirf `1` tha, jiski wajah se suggestions doosre elements ke peeche dikh rahi thi.

**Fix:**
`.search-wrap` ka `z-index` `1` se `1000` kar diya.

```css
.search-wrap {
  position: relative;
  z-index: 1000;
}
```

**Checked:**
Search karke check kiya. Ab suggestions doosre elements ke upar properly dikh rahi hain aur click bhi ho rahi hain.

**Time:**
- 10min

### CC-03 : "The menu has horizontal overflow on mobile"

**Reproduced:**
Mobile screen par menu/content screen ki width se bahar ja raha tha.

**Cause:**
Mobile layout mein kuch elements apni available width se zyada space le rahe the.

**Fix:**
Mobile layout mein `.name-btn` ki width ko `100%` kiya aur `.dish-card` mein `min-width: 0` add kiya.

**Checked:**
Mobile view mein 375px width par test kiya. Ab menu screen ke andar properly fit ho raha hai aur unnecessary horizontal page scrolling nahi hai.

**Time:**
[Apna actual time]
