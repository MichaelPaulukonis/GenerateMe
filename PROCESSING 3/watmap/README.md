# tweaks

## errors

```
currimg null
watmap.pde:271:0:271:0: NullPointerException
```


SIGH


## pass in args

<https://forum.processing.org/two/discussion/23924/handling-command-line-arguments-in-a-sketch>

<https://stackoverflow.com/questions/7341683/parsing-arguments-to-a-java-command-line-program>


## values

```
int THR = 20; // higher value bigger rectangles (1..200)
int MINR = 8; // minimum block (4..200)

int number_of_iterations = 50; // more = more variety
int number_of_blocks = 5; // more = more search tries
```

turning `number_of_iterations` to `1` produces crap

but as low as 5, with small block size produces recognizeable results
(in a solo image - what would happen if repeated and animated?)


The below (30,8,5,5) is eminently recognizeable on a NYT vs bl1000
but NOT vs bl1002 - which is "solid" w/ color variations
bl1000 is "empty" with things in it

```
int THR = 30; // higher value bigger rectangles (1..200)
int MINR = 8; // minimum block (4..200)

int number_of_iterations = 5; // more = more variety
int number_of_blocks = 5; // more = more search tries
```


```
final static int AVG_MODE = 0; // worst matching, difference of avgs of the luma
final static int ABS_MODE = 1; // difference of the luma each pixel
final static int DIST_MODE = 2; // best matching, distance between pixels colors (vectors)
```

`ABS_MODE` works best for me with black & white from color
AVG was no good

```
boolean do_blend = true; // blend image after process
int blend_mode = OVERLAY; // blend type
```

`do_blend` is not very strong w/ a black-n-white image. A little color.
