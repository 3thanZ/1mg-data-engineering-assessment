# Data Engineering Assessment

## Objective

To demonstrate the ability to process raw datasets into clean structured data and to use that data to produce derived datasets.

We will be looking at both the final results of your submission as well as the engineering and architectural choices made.

* Any language and / or framework is allowed but please provide clear, simple instructions on how to run. Please don't use anything that requires a special license or cost to use, open source preferred.
* It should be easy to run and evaluate. Simple, clear solutions preferred.
* It should be executable in a MacOS, Linux, Docker or notebook environment.
* Where possible please provide a public source code repository with commit history.
* Spend no longer than 3 hours but aim for less than 2. Focus on the main tasks. For example code to run in a repl or notebook is fine if it meets the requirements, rather than a compiled program. Feel free to add more features if you have time.
* Incomplete or non working submissions may be accepted if they demonstrate the main requirements

The assessment uses the freely available NYC taxi dataset available here:

https://registry.opendata.aws/nyc-tlc-trip-records-pds/


## Task

1. Create a program that produces a typed parquet file (https://parquet.apache.org/) from this file:

https://nyc-tlc.s3.us-east-1.amazonaws.com/trip%20data/green_tripdata_2013-09.csv

By typed we mean that the data is stored it a format that is correct for its type. For example, times are stored as timestamps, numbers as ints, doubles etc.

If you are unable to produce a parquet file use an alternative file format that also is strongly typed.

If you are short on time focus on typing the pick up and drop off times as well as the pick up and drop off locations.

2. Create a derived dataset, from the one created above, using a SQL statement that selects all existing columns and adds these new columns:

* One-Hot encoding for each hour of the day
* One-Hot encoding for each day	of the week
* Duration in seconds of the trip
* An int encoding to indicate if the pickup or dropoff locations were at JFK airport. (Use a bounding box from the GPS coordinates to determine this). Provide pseudo code if out of time. This column is optional.

Save the new dataset to parquet.

## Follow Up interview

If your submission is accepted we may contact you for a further interview. In this interview we will discuss your submission. We will discuss the choices made, their pros and cons as well as how your solution could be applied at scale in a cloud environment. Additionally, we will also ask what data privacy risks exist, if any, in the dataset and how you could handle those risks as well as how you could make the resulting datasets discoverable for other users.