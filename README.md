# Software Testing Project
## Distributed Video Contour Extractor

This project is a distributed contour extractor for video frames. Simply, the input is a video passed to the input node, which is on the back machine. The output is a file containing the coordinates of all contours at each frame, which is produced at the output node in the front machine. 

### Installation

```
python3 -m pip install --user -r requirements.txt
```

### Usage

First, edit remote addresses in config files. 
Then:
```
chmod +x sys_init.sh
./sys_init.sh <machine_type> <path_to_file> <processing_nodes_number>
```
__machine_type:__ 1 for back and 2 for front.

To reset used ports:
```
chmod +x reset_ports.sh
./reset_ports.sh
```

To run tests:
```
python -m pytest test_scripts/
```
-   Use `-q` to run in quiet mode.
-   Use `--full-trace` to print the stack trace of the failures.
-   Use `--testplan=<filename>.csv` to enumerate tests with their description and types without running them into a csv.
-   Use `--html=<filename>.html` to export an html report of tests and their results.