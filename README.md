# calibrate-stereo

For each observed point coordinate (u,v) the function computes:

x′′←(u−cx)/fx

y′′←(v−cy)/fy

(x′,y′)=undistort(x′′,y′′,distCoeffs)

[XYW]T←R∗[x′y′1]T

x←X/W
y←Y/W

only performed if P is specified:

u′←xf′x+c′x

v′←yf′y+c′y

where undistort is an approximate iterative algorithm that estimates the normalized original point coordinates out of the normalized distorted point coordinates ("normalized" means that the coordinates do not depend on the camera matrix).


input files:
- right[1..14].jpg
- left[1..14].jpg
- stereo_calib.xml

output files:
- intrinsics.yml
- extrinsics.yml


```xml
stereo_calib.xml:
---
<?xml version="1.0"?>
<opencv_storage>
<imagelist>
"left01.jpg"
"right01.jpg"
"left02.jpg"
"right02.jpg"
.. 
"left14.jpg"
"right14.jpg"
</imagelist>
</opencv_storage>
```


```yaml
intrinsics.yml:
---
M1:  
   rows: 3
   cols: 3
   dt: d
   data: [ 5.3398795381629998e+02, 0., 3.2838647414615605e+02, 0.,
       5.2871082254122143e+02, 2.3684272814037672e+02, 0., 0., 1. ]
D1:  
   rows: 1
   cols: 14
   dt: d
   data: [ -2.5896596034446923e-01, -1.2618399144051479e-01, 0., 0., 0.,
       0., 0., -3.9963356690988139e-01, 0., 0., 0., 0., 0., 0. ]
M2:  
   rows: 3
   cols: 3
   dt: d
   data: [ 5.3398795381629998e+02, 0., 3.1377033136474824e+02, 0.,
       5.2871082254122143e+02, 2.4187045537694971e+02, 0., 0., 1. ]
D2:  
   rows: 1
   cols: 14
   dt: d
   data: [ -2.6296219996246428e-01, -1.2154546771207121e-02, 0., 0., 0.,
       0., 0., -1.9510575516727410e-01, 0., 0., 0., 0., 0., 0. ]
```

```yaml
extrinsics.yml:
---
R: 
   rows: 3
   cols: 3
   dt: d
   data: [ 9.9997149582196887e-01, 4.8210106361039990e-03,
       5.8108002908933160e-03, -4.8866661262084174e-03,
       9.9992378065892118e-01, 1.1338137719252319e-02,
       -5.7556961129858961e-03, -1.1366209975903888e-02,
       9.9991883732282927e-01 ]
T:  
   rows: 3
   cols: 1
   dt: d
   data: [ -3.3427086816617235e+00, 4.6825937962329083e-02,
       3.6523404523280288e-03 ]
R1:  
   rows: 3
   cols: 3
   dt: d
   data: [ 9.9994753470257836e-01, -9.1729784965332052e-03,
       4.5589809977615928e-03, 9.1468661271598417e-03,
       9.9994182998349390e-01, 5.7158979446142759e-03,
       -4.6111476106960210e-03, -5.6738976694657908e-03,
       9.9997327174427453e-01 ]
R2:  
   rows: 3
   cols: 3
   dt: d
   data: [ 9.9990130032123892e-01, -1.4006998729557305e-02,
       -1.0925211603183612e-03, 1.4000549542530548e-02,
       9.9988572503331619e-01, -5.7027613580524850e-03,
       1.1722748835963793e-03, 5.6869026007070915e-03,
       9.9998314231311280e-01 ]
P1:  
   rows: 3
   cols: 4
   dt: d
   data: [ 4.3964859505829611e+02, 0., 3.1932437133789062e+02, 0., 0.,
       4.3964859505829611e+02, 2.3945363616943359e+02, 0., 0., 0., 1.,
       0. ]
P2:  
   rows: 3
   cols: 4
   dt: d
   data: [ 4.3964859505829611e+02, 0., 3.1932437133789062e+02,
       -1.4697622406427524e+03, 0., 4.3964859505829611e+02,
       2.3945363616943359e+02, 0., 0., 0., 1., 0. ]
Q: 
   rows: 4
   cols: 4
   dt: d
   data: [ 1., 0., 0., -3.1932437133789062e+02, 0., 1., 0.,
       -2.3945363616943359e+02, 0., 0., 0., 4.3964859505829611e+02, 0.,
       0., 2.9912905836118786e-01, 0. ]

```




Orthogonal | Screenshot
------------ | -------------

![screenshot](https://github.com/dparksports/inverse-projection/blob/master/pointcloud.png) |
![screenshot](https://github.com/dparksports/inverse-projection/blob/master/pointcloud.png)

