![Image](/img/BannerBBT.jpg)

(Photo: pixabay.com)

Big Bang Time & Planck Time
=========================

**Our present time calculation and time representation is based on the earth rotation and the earth movement around the sun, thus it is perfectly adapted for us humans on earth. However, it is less suitable for computers, in archaeology, astronomy and space travel. For these cases a new global time calculation is needed.**

... ![Image](/img/MF.png) *By Markus Fleschutz* 🕓 *September 16, 2017*

The reference date
---------------------------

Every time calculation has a point in time from which it is counted; such as the birthday or death anniversary of the founder of the religion or ruler. The reference date for the Big Bang Time (BBT) is the creation of the universe (Big Bang, Big Bang). The age of the universe was measured in 2013 by the Planck Space Telescope as follows: 13.82 ± 0.04 billion years. Thus, it is determined:

**BBT1 = January 1, 2013 00:00:00 UTC - 13,820,000,000 years**.

BBT1 means BBT version 1. version 1 therefore because the calculation of the time of the big bang should become more and more exact in the future. These new calculations are simply counted up as new versions (BBT2, BBT3 and so on).

The time division
-----------------------------

Each time calculation divides the time into sections. As time division for the BBT the standardized SI second (atomic second) is fixed. Humans as well as machines can easily deal with seconds, furthermore atomic clocks can measure them extremely accurately. The SI second is one of the basic units in the international SI system of units and has been defined as follows since 1967:

> The second is 9,192,631,770 times the period of the radiation corresponding to the transition between the two hyperfine structure levels of the ground state of atoms of the nuclide 133 Cs.
>

BBT times
--------------

A complete BBT time point is given as follows: **BBTn[+|-]SECONDS**, for example: BBT1+100 means 100 seconds after the Big Bang, BBT1+100,1 means 100 seconds and one tenth of a second after the Big Bang, and BBT1-1 means 1 second before the Big Bang.

January 1, 2013 00:00:00 UTC then corresponds to BBT1+436,126,032,000,000,000 since in SI units: 1 y = 31,557,600 s (365.25 days).

## BBT in the computer

For computers, provide for the storage of BBT in a signed data type of at least 64 bits (Minimum SignedInt64), plus the version number. Signed therefore to be able to represent the time before the big bang.

Most computers calculate internally with the Unixtime (seconds since January 1, 1970 00:00:00 UTC) and this time corresponds to BBT1+436.126.030.643.023.200. Thus applies for the conversion:

```
BBT1 = Unixtime + 436.126.030.643.023.200
```

and vice versa:

```
Unixtime = BBT1 - 436.126.030.643.023.200
```

## SI prefixes

For us humans, dealing with large numbers is not easy. Therefore the unit second is in use with different prefixes for units of measure (SI prefixes):

```
1 Ks = 1000 s (kilosecond, approx. 16.67 minutes)
1 Ms = 1,000,000 s (megasecond, approx. 11.57 days)
1 Gs = 1,000,000 s (gigasecond, approx. 31.69 years)
1 Ts = 1,000,000,000 s (terasecond, approx. 31,688.74 years)
1 Ps = 1,000,000,000 s (petasecond, approx. 31 million years)
1 Es = 1.000.000.000.000 s (exase second, approx. 758 billion years)
```

## The Planck Time (PT)

To make it easier for us humans to deal with the BBT, additional names like the Planck Time are introduced for reference times. It is valid:

**PT = BBT1+436,126,032,000,000,000** (Planck Time, January 1, 2013 00:00:00 UTC).

This name was introduced in honor of the measurement with the help of the Planck space telescope (the space telescope itself was switched off in the meantime). This automatically halves the complexity of the numbers, because PT stands for 436,126,032 * 10 ^ 9. A complete Plank time with at least 9 decimal places is then, for example:

**PT+000,000,000 = January 1, 2013 00:00:00 UTC**.

Example:

```
PT+123,456,789 = Friday, January 27, 2017 21:33:09 UTC
             ^------ seconds
            ^------- tens of seconds
           ^-------- hundredths of a second (approx. 1.66 minutes)
         ^---------- kiloseconds (1 Ks = about 16.67 minutes)
        ^----------- ten-kiloseconds (10 Ks = about 2.7 hours)
       ^------------ hundred kiloseconds (100 Ks = approx. 27.77 hours)
     ^-------------- megasecond (1 Ms = approx. 11.57 days)
    ^--------------- ten megasecond (10 Ms = approx. 115.7 days)
   ^---------------- hundred megasecond (100 Ms = approx. 1157.4 days)
```

Planck time is also easier to calculate with, for example:
PT+000,123,456 + 1000 seconds = PT+000,124,456. 

Further names for reference times will be introduced in due time.
