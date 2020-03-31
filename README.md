# ADCP_fixtime

Procedure to change or correct time data in a Teledyne RDI Workhorse binary data file.

## Requirements

* Python 3.X
* RDI Tools
	* BBConv
	* BBMerge

## Usage

To correct dates and times in an ADCP binary file (for instance, if the instrument was set to local time instead of UTC):

1. Clone the adcp_fixtime repository into a working directory of your choice. Copy the original uncorrected RDI binary data file into this directory.
1. Use the BBConv program (part of the RDI Tools software package) first to extract time and date information from the original binary file. Where the program asks for a decoder file, select TIME.DEC (included with RDI Tools). Save the output of this program to the working directory.
3. Open a command (terminal) window, navigate to the working directory and at the prompt, type: ```python adcp_fixtime.py <OFFSET> <INPUTFILE> <OUTPUTFILE>``` where OFFSET is the number of hours to adjust the time (can be positive or negative), INPUTFILE is the name of the file created by BBConv, and OUTPUTFILE is the desired name of the file to be created by the script.
4. Use the BBMerge program (included with RDI Tools) to add the corrected times and dates back to the ADCP data. Again, use TIME.DEC as the decoder file. This will create a new binary file in the working directory with the the corrected times and dates.

## Etc

Find this repository on [GitHub][github].

[github]:https://github.com/asmith-whoi/adcp_fixtime