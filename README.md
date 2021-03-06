# S3Scanner

A quick and dirty script to find unsecured S3 buckets and dump their contents :droplet:

## Using

The tool has 2 parts:

### 1 - s3finder.py
This script takes a list of domain names and checks if they're hosted on Amazon S3. Found S3 domains are output to file with their corresponding region in format "domain:region". 

![1 - s3finder.py](https://user-images.githubusercontent.com/3712226/36616997-726614a6-18ab-11e8-9dd3-c43715ef7355.png)

* **Install:**
  1. (Optional) `virtualenv venv && source ./venv/bin/activate`
  2. `pip install -r requirements.txt`

* **Usage:** 
  `$> python s3finder.py -o output.txt domainsToCheck.txt`

**Compatibility:**
Tested with Python 2.7 & 3.6

### 2 - s3dumper.sh
This script takes in a list of domains with regions made by s3finder.py. For each domain, it checks if there are publicly readable buckets and dumps them if so. 

**Usage:** `$> s3dumper.sh output.txt`

**Requirements:** [aws-cli](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)

![2 - s3dumper.sh](https://user-images.githubusercontent.com/3712226/30464321-8e8e6d34-9996-11e7-8739-94f13e082877.png)


## Current Status

* [![Build Status](https://travis-ci.org/sa7mon/S3Scanner.svg?branch=master)](https://travis-ci.org/sa7mon/S3Scanner) - master
   * [![Build Status](https://travis-ci.org/sa7mon/S3Scanner.svg?branch=enhancements)](https://travis-ci.org/sa7mon/S3Scanner) - enhancements
   * [![Build Status](https://travis-ci.org/sa7mon/S3Scanner.svg?branch=bugs)](https://travis-ci.org/sa7mon/S3Scanner) - bugs

## Contributing
Please make pull requests if you can improve on the code at all (which is certain as the code can be greatly optimized).

## License
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International [(CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
