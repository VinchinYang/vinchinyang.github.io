---
title: 'Point Cloud Library Basic Structure '
date: 2018-06-29
permalink: /posts/2018/06/point-cloud-library-basic-structure/
tags:
  - pcl
---
The basic type in PCL is a PointCloud. A pointcloud is a C++ class which contains the following data fields:



width(int)
======
Specifies the width of the point cloud dataset in the number of points. width has two meanings:

1. it can specify the total number of points in the cloud (equal with the number of elements in points – see below) for unorganized datasets;
1. it can specify the width (total number of points in a row) of an organized point cloud dataset.
```
cloud.width = 640; // there are 640 points per line
```

height(int)
======
Specifies the height of the point cloud dataset in the number of points. height has two meanings:

1. it can specify the height (total number of rows) of an organized point cloud dataset;
1. it is set to 1 for unorganized datasets (thus used to check whether a dataset is organized or not).

```
cloud.width = 640; // image-like organized structure, with 640 rows and 480 colums,
cloud.height = 480; // thus 640*480 = 307200 points total in the dataset
```

```
cloud.width = 307200;
cloud.height = 1; // unorganized point cloud dataset with 307200 points
```

points(std::vector<PointT>)
======
Contains the data array where all the points of type PointT are stored. For example, for a cloud containing XYZ data, points contains a vector of pcl::PointXYZ elements:
```
pcl::PointCloud<pcl::PointXYZ> cloud;
std::vector<pcl::PointXYZ> data = cloud.points;
```
1. is dense(bool)
Specifies if all the data in points is finite (true), or whether the XYZ values of certain points might contain Inf/NaN values (false).
1. sensor origin(Eigen::Vector4f)
Specifies the sensor acquisition pose (origin/translation). This member is usually optional, and not used by the majority of the algorithms in PCL.
1. sensor orientation(Eigen::Quaternionf)
Specifies the sensor acquisition pose (orientation). This member is usually optional, and not used by the majority of the algorithms in PCL.

The PointT type is the primary point data type and describes what each individual element of points holds. PCL comes with a large variety of different point types, most explained in the Adding your own custom PointT type tutorial.