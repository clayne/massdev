massdev
=======

Massive Dev Chart command line tools

Rational
========
This started out as a tool to group dissimilar film/ei combos within the same developer/dilution by time - allowing one
to develop batches of different films together if they're "close enough". It then morphed into a useful command line tool
for quickly dumping film/dev combos.

Examples
========

Find times for a bunch of different film/ei combos in rodinal 1+50 and xtol:
```
$ massdev -d rodinal:1+50,xtol 'neopan 1600:1600-' 'tri-x 400:200-800' 'hp5:800' 'apx 100:100'
# dev                             dil                     film       ei  time_sf  time_mf  time_lf     temp notes
rodinal                          1+50              neopan 1600     1600        8                        20c 
rodinal                          1+50                tri-x 400      200        9        9               20c 
rodinal                          1+50                tri-x 400      320      9.5      9.5               20c [1]
rodinal                          1+50                  apx 100      100       13       13       13      20c 
rodinal                          1+50                tri-x 400      400       13       13               20c [29]
rodinal                          1+50                tri-x 400      800       13       13               23c 
rodinal                          1+50                tri-x 400      640     15.5     15.5               20c [29]
rodinal                          1+50                     hp5+      800       16       16       16      20c 
rodinal                          1+50                tri-x 400      800     16.5     16.5               20c [29]

xtol                            stock                tri-x 400  100-200      5.5      5.5               20c [29]
xtol                            stock              neopan 1600     1600     5.75                        20c 
xtol                            stock              neopan 1600     3200      6.5                        20c 
xtol                            stock                  apx 100      100     6.75     6.75     6.75      20c [30]
xtol                            stock                tri-x 400      400     6.75     6.25               20c [29]
xtol                            stock                tri-x 400      400        7        7               20c 
xtol                            stock              neopan 1600     6400     7.25                        20c 
xtol                            stock                tri-x 400      800     7.75        7               20c [29]
xtol                            stock                     hp5+      800     10.5     10.5     10.5      20c 

xtol                              1+1              neopan 1600     1600      7.5                        20c 
xtol                              1+1                tri-x 400      250     7.75     7.75               20c [a10]
xtol                              1+1                tri-x 400  100-200        8     6.75               20c [29]
xtol                              1+1              neopan 1600     3200      8.5                        20c 
xtol                              1+1                tri-x 400      400     8.75        8               20c [29]
xtol                              1+1                tri-x 400      400        9        9               20c 
xtol                              1+1                  apx 100      100     9.75     9.75     9.75      20c [30]
xtol                              1+1              neopan 1600     6400     9.75                        20c 
xtol                              1+1                tri-x 400      800       10     9.25               20c [29]
xtol                              1+1                     hp5+      800    14.25    14.25    14.25      20c 

xtol                              1+2                tri-x 400  100-200     8.75      8.5               20c [29]
xtol                              1+2              neopan 1600     1600       10                        20c 
xtol                              1+2                tri-x 400      400     10.5    10.25               20c [29]
xtol                              1+2              neopan 1600     3200    11.25                        20c 
xtol                              1+2                tri-x 400      800     12.5       12               20c [29]
xtol                              1+2              neopan 1600     6400       13                        20c 
xtol                              1+2                  apx 100      100    13.75    13.75    13.75      20c [30]
xtol                              1+2                     hp5+      800       18       18       18      20c 

xtol                            1+2.5              neopan 1600     1600     11.5                        20c 

xtol                              1+3                tri-x 400  100-200    10.75      9.5               20c [29]
xtol                              1+3                tri-x 400      400     12.5       11               20c [29]
xtol                              1+3              neopan 1600     1600       13                        20c 
xtol                              1+3                tri-x 400      400       13       13               20c [37]
xtol                              1+3                tri-x 400      800       14     13.5               20c [29]
xtol                              1+3              neopan 1600     3200    14.75                        20c 
xtol                              1+3              neopan 1600     6400     16.5                        20c 
xtol                              1+3                  apx 100      100    17.25    17.25    17.25      20c [30]
xtol                              1+3                     hp5+      800       23       23       23      20c 
```

Times for Tri-X in XTOL:
```
$ massdev 'tri-x 400' -d xtol
# dev                             dil                     film       ei  time_sf  time_mf  time_lf     temp notes
xtol                            stock                tri-x 400  100-200      5.5      5.5               20c [29]
xtol                            stock                tri-x 400      400     6.75     6.25               20c [29]
xtol                            stock                tri-x 400      400        7        7               20c 
xtol                            stock                tri-x 400     1600        7        7               24c 
xtol                            stock                tri-x 400      800     7.75        7               20c [29]
xtol                            stock                tri-x 400     1600        9     8.75               20c [29]
xtol                            stock                tri-x 400     1600     9.75     9.75               20c 
xtol                            stock                tri-x 400     3200     10.5    10.25               20c [29]
xtol                            stock                tri-x 400     3200     11.5     11.5               20c 

xtol                              1+1                tri-x 400      250     7.75     7.75               20c [a10]
xtol                              1+1                tri-x 400  100-200        8     6.75               20c [29]
xtol                              1+1                tri-x 400      400     8.75        8               20c [29]
xtol                              1+1                tri-x 400      400        9        9               20c 
xtol                              1+1                tri-x 400      800       10     9.25               20c [29]
xtol                              1+1                tri-x 400     1600    11.75       11               20c [29]
xtol                              1+1                tri-x 400     1600    13.25    13.25               20c 
xtol                              1+1                tri-x 400     3200     13.5     13.5               20c [29]
xtol                              1+1                tri-x 400     3200     15.5     15.5               20c 

xtol                              1+2                tri-x 400  100-200     8.75      8.5               20c [29]
xtol                              1+2                tri-x 400      400     10.5    10.25               20c [29]
xtol                              1+2                tri-x 400      800     12.5       12               20c [29]
xtol                              1+2                tri-x 400     1600     14.5     14.5               20c [29]
xtol                              1+2                tri-x 400     3200       17       17               20c [29]

xtol                              1+3                tri-x 400  100-200    10.75      9.5               20c [29]
xtol                              1+3                tri-x 400      400     12.5       11               20c [29]
xtol                              1+3                tri-x 400      400       13       13               20c [37]
xtol                              1+3                tri-x 400      800       14     13.5               20c [29]
xtol                              1+3                tri-x 400     1600     16.5    16.25               20c [29]
xtol                              1+3                tri-x 400     3200       20    19.75               20c [29]
```

Times for Agfapan APX 100 in Rodinal:
```
$ massdev 'apx 100' -d rodinal
# dev                             dil                     film       ei  time_sf  time_mf  time_lf     temp notes
rodinal                          1+24                  apx 100       64      7.5      7.5      7.5      20c [30]

rodinal                          1+25                  apx 100      100        8        8        8      20c 
rodinal                          1+25                  apx 100      200       11       11       11      20c [30]

rodinal                          1+50                  apx 100       50     11.5     11.5     11.5      20c [30]
rodinal                          1+50                  apx 100      100       13       13       13      20c 
rodinal                          1+50                  apx 100      160       17       17       17      20c 
rodinal                          1+50                  apx 100      200     21.5     21.5     21.5      20c 
rodinal                          1+50                  apx 100      400       29       29       29      20c 
```

Neopan in XTOL 1+1:
```
$ massdev neopan -d xtol:1+1
# dev                             dil                     film       ei  time_sf  time_mf  time_lf     temp notes
xtol                              1+1              neopan 1600      200      5.5                        20c 
xtol                              1+1              neopan 1600      400        6                        20c 
xtol                              1+1              neopan 1600      800     6.75                        20c 
xtol                              1+1              neopan 1600     1600      7.5                        20c 
xtol                              1+1               neopan 400  100-200     8.25     8.25               20c 
xtol                              1+1              neopan 1600     3200      8.5                        20c 
xtol                              1+1         neopan 100 acros      100      9.5       10      9.5      20c 
xtol                              1+1             neopan 100ss      100      9.5      9.5               20c 
xtol                              1+1              neopan 1600     6400     9.75                        20c 
xtol                              1+1               neopan 400      400     9.75     9.75               20c 
xtol                              1+1               neopan 400      800     11.5     11.5               20c 
xtol                              1+1         neopan 100 acros      200       13       13       13      20c [15]
xtol                              1+1               neopan 400     1600     13.5     13.5               20c 
xtol                              1+1               neopan 400     3200     16.5     16.5               20c 
```

Caveats
=======

1. Lame HTML mangling because the data from MDC is not structured in anything but HTML.
2. Requires html2text due to #1.
3. No notes displayed.
