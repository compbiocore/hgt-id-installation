## Running

Importantly, it is necessary to run the main perl script **from within the HGT-ID root directory** - attempting to run it from anywhere else will result in a failure to locate the configuration file.  Thus, the command will begin with some variant of:

        perl src/hgt.pl [arguments]

Running from within the `src` directory will fail, even if the correct configuration file path is provided.
