```python
from PIL import Image
from io import BytesIO
import matplotlib.pyplot as plt
import pandas as pd

csv_path = 'C:\\Niteen\\Data_Science\\dataset\\xray-image-data.csv'
data = pd.read_csv(csv_path, sep=',', header=None)
```


```python
import requests
```


```python
for index in range(1, len(data)): 
  print("Image #{}: {}\nHas pneumonia: {}".format(index, data[0][index], data[1][index]))
  response = requests.get(data[0][index])
  img = Image.open(BytesIO(response.content))
  fig = plt.figure(figsize=(6, 6))
  plt.imshow(img, cmap='gray', vmin=0, vmax=255)
  plt.show()
```

    Image #1: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8060_img-0302/img-0302.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_1.png)


    Image #2: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8065_im-0030/im-0030.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_3.png)


    Image #3: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e0_img304-0101-625/img304-0101-625.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_5.png)


    Image #4: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cc_img278-0101-572/img278-0101-572.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_7.png)


    Image #5: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cb_img834-im1002-2747/img834-im1002-2747.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_9.png)


    Image #6: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8060_im-0013/im-0013.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_11.png)


    Image #7: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad805d_im-0043/im-0043.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_13.png)


    Image #8: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c6_img326-0101-672/img326-0101-672.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_15.png)


    Image #9: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8063_img-0317/img-0317.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_17.png)


    Image #10: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8061_im-0050/im-0050.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_19.png)


    Image #11: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c4_img363-0101-742/img363-0101-742.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_21.png)


    Image #12: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75df_img277-im1002-1303/img277-im1002-1303.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_23.png)


    Image #13: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8061_im-0086/im-0086.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_25.png)


    Image #14: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c5_img132-0101-266/img132-0101-266.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_27.png)


    Image #15: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c8_img278-0101-573/img278-0101-573.jpeg
    Has pneumonia: 1
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_29.png)


    Image #16: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad805f_im-0011-0001-0002/im-0011-0001-0002.jpeg
    Has pneumonia: 0
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_31.png)


    Image #17: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad808c_img-im-0927-0001/img-im-0927-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_33.png)


    Image #18: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8090_img-im-1127-0001/img-im-1127-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_35.png)


    Image #19: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8064_img-0278/img-0278.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_37.png)


    Image #20: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cd_img341-im1002-1577/img341-im1002-1577.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_39.png)


    Image #21: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c9_img441-im1002-1912/img441-im1002-1912.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_41.png)


    Image #22: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8091_img-im-1204-0001/img-im-1204-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_43.png)


    Image #23: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8064_im-0041/im-0041.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_45.png)


    Image #24: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cc_img383-im1002-1749/img383-im1002-1749.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_47.png)


    Image #25: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75de_img544-0101-1076/img544-0101-1076.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_49.png)


    Image #26: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d1_img947-0101-1618/img947-0101-1618.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_51.png)


    Image #27: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8062_im-00-m01-33-0001/im-00-m01-33-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_53.png)


    Image #28: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d9_img1051-im1002-2985/img1051-im1002-2985.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_55.png)


    Image #29: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8080_img-im-0578-0001/img-im-0578-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_57.png)


    Image #30: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8089_img-im-0925-0001/img-im-0925-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_59.png)


    Image #31: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e1_img357-im1002-1640/img357-im1002-1640.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_61.png)


    Image #32: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c9_img712-0101-1310/img712-0101-1310.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_63.png)


    Image #33: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8065_im-im1002-01/im-im1002-01.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_65.png)


    Image #34: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c7_img332-im1002-1537/img332-im1002-1537.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_67.png)


    Image #35: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807a_im-0672-0001/im-0672-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_69.png)


    Image #36: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d0_img575-0101-1119/img575-0101-1119.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_71.png)


    Image #37: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cd_img262-0101-544/img262-0101-544.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_73.png)


    Image #38: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807f_img-im-0555-0001-0001/img-im-0555-0001-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_75.png)


    Image #39: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8085_img-im-0776-0001/img-im-0776-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_77.png)


    Image #40: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d7_img437-0101-888/img437-0101-888.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_79.png)


    Image #41: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8083_img-im-0601-0001/img-im-0601-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_81.png)


    Image #42: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8094_img-im-1440-0001/img-im-1440-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_83.png)


    Image #43: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d9_img375-0101-758/img375-0101-758.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_85.png)


    Image #44: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8069_im-0290-0001/im-0290-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_87.png)


    Image #45: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8091_img-im-1223-0001/img-im-1223-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_89.png)


    Image #46: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8066_img-0300/img-0300.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_91.png)


    Image #47: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75eb_img600-0101-1156/img600-0101-1156.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_93.png)


    Image #48: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ca_img3-im1002-10/img3-im1002-10.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_95.png)


    Image #49: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ca_img276-im1002-1299/img276-im1002-1299.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_97.png)


    Image #50: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ce_img889-im1002-2813/img889-im1002-2813.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_99.png)


    Image #51: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75da_img126-0101-255/img126-0101-255.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_101.png)


    Image #52: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807e_img-im-0486-0001/img-im-0486-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_103.png)


    Image #53: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75eb_img647-0101-1228/img647-0101-1228.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_105.png)


    Image #54: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d2_img755-0101-1382/img755-0101-1382.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_107.png)


    Image #55: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad808f_img-im-1058-0001/img-im-1058-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_109.png)


    Image #56: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8090_img-im-1102-0001-0002/img-im-1102-0001-0002.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_111.png)


    Image #57: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75dc_img918-0101-1575/img918-0101-1575.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_113.png)


    Image #58: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8078_im-0643-0001/im-0643-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_115.png)


    Image #59: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ec_img442-0101-900/img442-0101-900.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_117.png)


    Image #60: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807c_img-im-0419-0001/img-im-0419-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_119.png)


    Image #61: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cf_img325-0101-664/img325-0101-664.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_121.png)


    Image #62: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c7_img371-im1002-1700/img371-im1002-1700.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_123.png)


    Image #63: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807e_img-im-0531-0001/img-im-0531-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_125.png)


    Image #64: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807c_im-0764-0001/im-0764-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_127.png)


    Image #65: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8067_im-0226-0001/im-0226-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_129.png)


    Image #66: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8084_img-im-0619-0001/img-im-0619-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_131.png)


    Image #67: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad806e_im-0520-0001/im-0520-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_133.png)


    Image #68: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d6_img44-im1002-218/img44-im1002-218.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_135.png)


    Image #69: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cf_img258-im1002-1206/img258-im1002-1206.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_137.png)


    Image #70: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d6_img88-0101-161/img88-0101-161.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_139.png)


    Image #71: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75db_img348-0101-714/img348-0101-714.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_141.png)


    Image #72: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d4_img896-0101-1548/img896-0101-1548.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_143.png)


    Image #73: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8081_img-im-0585-0001/img-im-0585-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_145.png)


    Image #74: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75dd_img662-im1002-2554/img662-im1002-2554.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_147.png)


    Image #75: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d0_img597-im1002-2451/img597-im1002-2451.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_149.png)


    Image #76: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d5_img140-0101-284/img140-0101-284.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_151.png)


    Image #77: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ca_img600-im1002-2456/img600-im1002-2456.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_153.png)


    Image #78: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cd_img680-im1002-2575/img680-im1002-2575.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_155.png)


    Image #79: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e7_img556-0101-1096/img556-0101-1096.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_157.png)


    Image #80: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad808e_img-im-0999-0001/img-im-0999-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_159.png)


    Image #81: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad806f_im-0546-0001/im-0546-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_161.png)


    Image #82: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8083_img-im-0609-0001/img-im-0609-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_163.png)


    Image #83: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d9_img328-im1002-1514/img328-im1002-1514.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_165.png)


    Image #84: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c7_img731-im1002-2633/img731-im1002-2633.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_167.png)


    Image #85: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e9_img445-0101-916/img445-0101-916.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_169.png)


    Image #86: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c9_img328-im1002-1513/img328-im1002-1513.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_171.png)


    Image #87: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d0_img453-0101-935/img453-0101-935.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_173.png)


    Image #88: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8093_img-im-1341-0001/img-im-1341-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_175.png)


    Image #89: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e0_img124-0101-239/img124-0101-239.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_177.png)


    Image #90: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ce_img661-0101-1245/img661-0101-1245.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_179.png)


    Image #91: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad806a_im-0451-0001/im-0451-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_181.png)


    Image #92: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75db_img393-0101-784/img393-0101-784.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_183.png)


    Image #93: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75dd_img718-0101-1316/img718-0101-1316.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_185.png)


    Image #94: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad807d_img-im-0466-0001/img-im-0466-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_187.png)


    Image #95: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8092_img-im-1261-0001/img-im-1261-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_189.png)


    Image #96: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75c7_img419-0101-859/img419-0101-859.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_191.png)


    Image #97: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad806b_im-0493-0001/im-0493-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_193.png)


    Image #98: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8086_img-im-0860-0001/img-im-0860-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_195.png)


    Image #99: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad808f_img-im-1060-0001/img-im-1060-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_197.png)


    Image #100: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cd_img559-im1002-2329/img559-im1002-2329.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_199.png)


    Image #101: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8093_img-im-1334-0001/img-im-1334-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_201.png)


    Image #102: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75ec_img688-im1002-2584/img688-im1002-2584.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_203.png)


    Image #103: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d3_img542-im1002-2276/img542-im1002-2276.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_205.png)


    Image #104: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8087_img-im-0907-0001/img-im-0907-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_207.png)


    Image #105: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad808d_img-im-0936-0001/img-im-0936-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_209.png)


    Image #106: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8085_img-im-0647-0001/img-im-0647-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_211.png)


    Image #107: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75da_img458-im1002-1952/img458-im1002-1952.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_213.png)


    Image #108: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d3_img359-im1002-1645/img359-im1002-1645.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_215.png)


    Image #109: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75e2_img410-0101-821/img410-0101-821.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_217.png)


    Image #110: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8088_img-im-0919-0001/img-im-0919-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_219.png)


    Image #111: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8066_img-0285/img-0285.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_221.png)


    Image #112: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75df_img507-im1002-2141/img507-im1002-2141.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_223.png)


    Image #113: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8077_im-0618-0001/im-0618-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_225.png)


    Image #114: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75cf_img40-im1002-202/img40-im1002-202.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_227.png)


    Image #115: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d4_img278-0101-575/img278-0101-575.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_229.png)


    Image #116: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad8073_im-0580-0001/im-0580-0001.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_231.png)


    Image #117: https://s3.amazonaws.com/video.udacity-data.com/topher/2019/April/5cad75d7_img354-im1002-1633/img354-im1002-1633.jpeg
    Has pneumonia: nan
    


![png](x_ray_analyzer_files/x_ray_analyzer_2_233.png)



```python

```
