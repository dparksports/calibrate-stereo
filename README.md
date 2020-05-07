# calibrate-stereo

input files:
right[1..14].jpg
left[1..14].jpg
stereo_calib.xml

output files:
extrinsics.yml
intrinsics.yml


```yaml
en:
  errors:
    format: "%{attribute} %{message}"
    messages:
      confirmation: "doesn't match %{attribute}"
      accepted: "must be accepted"
      wrong_length:
        one: "is the wrong length (should be 1 character)"
        other: "is the wrong length (should be %{count} characters)"
      equal_to: "must be equal to %{count}"
```


```yaml
en:
%YAML:1.0
---
M1: !!opencv-matrix
   rows: 3
   cols: 3
   dt: d
   data: [ 5.3398795381629998e+02, 0., 3.2838647414615605e+02, 0.,
       5.2871082254122143e+02, 2.3684272814037672e+02, 0., 0., 1. ]
D1: !!opencv-matrix
   rows: 1
   cols: 14
   dt: d
   data: [ -2.5896596034446923e-01, -1.2618399144051479e-01, 0., 0., 0.,
       0., 0., -3.9963356690988139e-01, 0., 0., 0., 0., 0., 0. ]
M2: !!opencv-matrix
   rows: 3
   cols: 3
   dt: d
   data: [ 5.3398795381629998e+02, 0., 3.1377033136474824e+02, 0.,
       5.2871082254122143e+02, 2.4187045537694971e+02, 0., 0., 1. ]
D2: !!opencv-matrix
   rows: 1
   cols: 14
   dt: d
   data: [ -2.6296219996246428e-01, -1.2154546771207121e-02, 0., 0., 0.,
       0., 0., -1.9510575516727410e-01, 0., 0., 0., 0., 0., 0. ]
```


Left Rectified | Right Rectified
------------ | -------------
Left Optical Center | Right Optical Center
![cell 1](https://github.com/dparksports/calibrate-stereo/blob/master/cmake-build-debug/left02.jpg) | ![cell 2](https://github.com/dparksports/calibrate-stereo/blob/master/cmake-build-debug/right02.jpg)

![cell 3](https://github.com/dparksports/calibrate-stereo/blob/master/stereo-calib-1-rectified.jpg)
