# Using gperf / gperftools / pprof

INSTALLATION  
1. Clone the repository from https://github.com/gperftools/gperftools
1. Install manually
```bash
sh autogen.sh
./configure
make
sudo make install
sudo /sbin/ldconfig
```

USAGE  
1. Recompile the code with `-lprofiler`
1. Check that the library is linked with `ldd [executable]`. `libprofiler.so.0` should appear. If not, recompile with `-Wl,--no-as-needed -lprofiler`.
1. Run `CPUPROFILE_FREQUENCY=1000 CPUPROFILE=/tmp/[executable].prof [exectuable] ... (arguments)`
1. `pprof --pdf [executable] /tmp/[executable].prof > profile.pdf`

REFERENCES  
1. https://stackoverflow.com/q/46949407/1248687  
1. https://stackoverflow.com/q/1581494/1248687

