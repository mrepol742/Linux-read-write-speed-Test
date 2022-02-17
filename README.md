<p align="center">
  <img src="https://img.icons8.com/nolan/64/linux--v2.png" width="300px"/>
  <h1 align="center">Linux UNIX I/O Speed Test</h1>
</p>
<br> <br>

**dd command is useful in finding simple read and write performance in Linux**

~~~
sudo dd if=/dev/input.file  of=/path/to/output.file  bs=block-size  count=number-of-blocks  oflag=dsync
~~~
Adjust the ***block-size*** and ***number-of-blocks*** as per needs and your device setup.

<h1>Samples:</h1>

~~~
sudo dd if=/dev/zero of=/tmp/test1.img bs=1G count=1 oflag=dsync
~~~
Output:
~~~
mrepol742@APTX-4869:~$ sudo dd if=/dev/zero of=/tmp/test1.img bs=1G count=1 oflag=dsync
[sudo] password for mrepol742:          
1+0 records in
1+0 records out
1073741824 bytes (1.1 GB, 1.0 GiB) copied, 13.1838 s, 81.4 MB/s
mrepol742@APTX-4869:~$
~~~
#
~~~
sudo dd if=/dev/zero of=/tmp/test2.img bs=64M count=1 oflag=dsync
~~~
Output:
~~~
mrepol742@APTX-4869:~$ sudo dd if=/dev/zero of=/tmp/test2.img bs=64M count=1 oflag=dsync
1+0 records in
1+0 records out
67108864 bytes (67 MB, 64 MiB) copied, 0.782544 s, 85.8 MB/s
mrepol742@APTX-4869:~$ 
~~~
#
~~~
sudo dd if=/dev/zero of=/tmp/test3.img bs=1M count=256 conv=fdatasync
~~~
Output:
~~~
mrepol742@APTX-4869:~$ sudo dd if=/dev/zero of=/tmp/test3.img bs=1M count=256 conv=fdatasync
256+0 records in
256+0 records out
268435456 bytes (268 MB, 256 MiB) copied, 2.996 s, 89.6 MB/s
mrepol742@APTX-4869:~$
~~~
#
~~~
sudo dd if=/dev/zero of=/tmp/test4.img bs=8k count=10k
~~~
Output:
~~~
mrepol742@APTX-4869:~$ sudo dd if=/dev/zero of=/tmp/test4.img bs=8k count=10k
10240+0 records in
10240+0 records out
83886080 bytes (84 MB, 80 MiB) copied, 0.179225 s, 468 MB/s
mrepol742@APTX-4869:~$
~~~
#
~~~
sudo dd if=/dev/zero of=/tmp/test4.img bs=512 count=1000 oflag=dsync
~~~
Output:
~~~
mrepol742@APTX-4869:~$ sudo dd if=/dev/zero of=/tmp/test4.img bs=512 count=1000 oflag=dsync
1000+0 records in
1000+0 records out
512000 bytes (512 kB, 500 KiB) copied, 41.4651 s, 12.3 kB/s
mrepol742@APTX-4869:~$
~~~
