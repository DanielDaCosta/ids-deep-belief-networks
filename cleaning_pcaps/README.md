# Cleaning Pcaps 
This directory contains the scripts used to "clean" the raw pcaps provided as part of the CIC IDS 2017 dataset.
The steps performed include but are not limited to:

1. Packet Deduplication:

The Sally Floyd and Vern Paxxson papers read in class brought to our attention that traffic captured via tools such as wireshark may contain duplicates. 
In order to remediatet this issue editcap was used to remove duplicate packets from the pcaps.

This resulted in the following reductions to the original pcaps:
Monday Traffic - From to 10,822,507,416 bytes to 10,737,846,120 bytes (Reduced by 0.7823%)
Tuesday Traffic - From 11,048,283,608 bytes to 10,968,829,792 bytes (Reduced by 0.7192%)
Wednesday Traffic - From 13,420,789,612 bytes to 13,342,573,764 bytes (Reduced by 0.5828%)
Thursday Traffic - From 8,302,500,180 bytes to 8,221,154,268 bytes (Reduced by 0.9798%)
Friday Traffic - From 8,839,309,056 bytes To 8,762,558,668 bytes (Reduced by 0.8683%)

2. Attack Traffic Extraction: 

The researchers who created the dataset provide detailed timeline for when each attack was executied in their paper "Toward Generating a New Intrusion Detection Dataset and Intrusion" and the website associated with the dataset.

Using editcap and the aformentioned times we extracted all traffic that occured in the time frames listed from the deduplicated pcacps. 
We are aware that the data extracted still contains begnin traffic and which requires further processing.

3. Preliminary Stream Extraction:

In order to begin extracting features we sampled 1% of the TCP & UDP streams found in the pcaps.