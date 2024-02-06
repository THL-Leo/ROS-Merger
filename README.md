# ROS-Merger
A lab project I completed at ILab@USC. The main purpose of this jupyter notebook is to combine multiple out of sync bag files into one. There are many bag file merger out there but they are always tailored for each project's specific use. This merger will set a reference timestamp and align all of the image timestamp by adding the differences. Afterwards, use a 3rd party ROS viewer such as FoxGlove Studio to view the file. SQL will handle the out of order messages. 

Github Issue link: https://github.com/klekkala/vision_toolkit/issues/2

Input folder: raw_data/2023_\*_\*/cam{1..5}/*.bag

Output folder: merged_bag/2023_\*_\*/session*.bag

## Running

```
$ python3 /content/drive/MyDrive/merged_bag/merge.py -s 1 -o /content/drive/MyDrive/merged_bag/2023_03_28/ -i ./cam1/test_2023-03-28-11-29-55.bag ./cam2/test_2023-12-30-16-46-21.bag ./cam3/test_2023-12-30-16-46-21.bag ./cam4/test_2023-03-02-05-01-04.bag ./cam5/test_2023-03-02-05-00-52.bag
```

## Command line options

* -h: Prints out a list of available command line options and their purposes. 
* -i infile: Specify the input files to merge. There needs to be at least one or more .bag files.
* -o outfile: Specify the output file path to store the merged bag file.
* -s: Specifies the session number for identifying file purposes.
