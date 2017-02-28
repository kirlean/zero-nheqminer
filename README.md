# Build instructions:

### Dependencies:
  - Boost 1.54+

## Linux

Working solvers CPU_TROMP

## Linux (Ubuntu 14.04 / 16.04) Build CPU_XENONCAT:

 - Open terminal and run the following commands:
   - `sudo apt-get install cmake build-essential libboost-all-dev`
   - `git clone  https://github.com/ocminer/zero-nheqminer.git`
   - `cd zero-nheqminer`
   - `cd Linux_cmake/nheqminer_cpu_tromp`
   - `cmake .`
   - `make -j $(nproc)`
   

# Run instructions:

Parameters: 
	-h		Print this help and quit
	-l [location]	Stratum server:port
	-u [username]	Username (bitcoinaddress)
	-a [port]	Local API port (default: 0 = do not bind)
	-d [level]	Debug print level (0 = print all, 5 = fatal only, default: 2)
	-b [hashes]	Run in benchmark mode (default: 200 iterations)

CPU settings
	-t [num_thrds]	Number of CPU threads
	-e [ext]	Force CPU ext (0 = SSE2, 1 = AVX, 2 = AVX2)

NVIDIA CUDA settings
	-ci		CUDA info
	-cd [devices]	Enable CUDA mining on spec. devices
	-cb [blocks]	Number of blocks
	-ct [tpb]	Number of threads per block
Example: -cd 0 2 -cb 12 16 -ct 64 128

If run without parameters, miner will start mining with 75% of available logical CPU cores. Use parameter -h to learn about available parameters:

Example to run benchmark on your CPU:

        nheqminer -b
        
Example to mine on your CPU with your registered suprnova worker:

        nheqminer -l zero.suprnova.cc:6568 -u yourusername.worker1 -e 0 -t 2

