# scripts
small useful scripts

##mtrace gdb scripts
to start mtracing process, run

```bash
gdb -x gdb_enable_mtrace.txt -p $pid
```

to stop mtracing run

```bash
gdb -x gdb_disable_mtrace.txt -p $pid
```

this will output memory events to /tmp/$prog_name.trace (e.g. /tmp/my_program.trace)

after saving memory log run
```bash
mtrace $binary_file log.trace > out.txt
```

to generate human-readable output with all potential memory leaks e.g.
```bash
mtrace /usr/bin/my_program /tmp/my_program.trace > out.txt
```
