# mso2eapo

*By Etienne Dechamps (etienne@edechamps.fr)*

`mso2eapo` is a small shell script for converting [Multi-Sub Optimizer][]
"Filter Reports" to an [Equalizer APO][] configuration file. This avoids having
to copy the filter parameters by hand, which is tedious and error-prone.

## Limitations

- Only supports *Gain Block*, *Delay Block*, *Parametric EQ*,
  *Parametric EQ (RBJ)*, *HPF Butterworth 12 dB/oct*, and
  *LPF Butterworth 12 dB/oct* filter types, for now.
- Because the MSO filter report does not include information about topology
  (i.e. filter channels), all filters are dumped into a single file/chain. Any
  splitting has to be done by hand.

## Prerequisites

- Bash.

## How to use

`mso2eapo` takes the MSO Filter Report as standard input, and the standard
output is in Equalizer APO configuration file format. There are no options.

```shell
$ mso2eapo < filter-report.txt > equalizer-apo-config.txt
```

[Equalizer APO]: https://sourceforge.net/projects/equalizerapo/
[Multi-Sub Optimizer]: https://www.andyc.diy-audio-engineering.org/mso/html/index.html