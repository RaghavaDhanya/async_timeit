# Async Timeit
Replica of default python [timeit](https://docs.python.org/3/library/timeit.html) module with small changes to allow async functions and await keyword.

All CLI options should work as same from the original module.
Taken from this exact [commit](https://github.com/python/cpython/blob/562c13f5734d406b2283cfca673611f4b496fdc7/Lib/timeit.py).


## Example usage
```shell
$python timeit.py -n 5 -r 5 -s "import asyncio" 'await asyncio.sleep(2)'
5 loops, best of 5: 2 sec per loop

$python timeit.py -n 5 -r 5 -s "import asyncio" 'await asyncio.sleep(2)
await asyncio.sleep(2)'
5 loops, best of 5: 4 sec per loop

$python timeit.py -n 5 -r 5 -s "import asyncio" 'await asyncio.gather(asyncio.sleep(2),asyncio.sleep(2))'
5 loops, best of 5: 2 sec per loop
```

## Warning
This is not extensively tested. Also unsure if timeit can be reliably used for async code. 


## License
All original python library code is under PSF's original license. 
Any of my contributions are under Apache 2.0
