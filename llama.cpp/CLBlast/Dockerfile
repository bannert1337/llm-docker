FROM ubuntu:latest

# Install Dependencies
RUN apt-get update && apt-get install -y cmake git curl build-essential 

# Install OpenCL library
RUN apt install -y ocl-icd-opencl-dev
RUN apt install -y intel-opencl-icd

# Install CLBlast library
RUN apt install -y libclblast-dev

# CLBlast
RUN apt install -y opencl-headers ocl-icd

# Clone the project files into the Docker image
RUN git clone https://github.com/ggerganov/llama.cpp

# Set the working directory to the project directory
WORKDIR /llama.cpp

# build with CLBlast support
RUN make LLAMA_CLBLAST=1
