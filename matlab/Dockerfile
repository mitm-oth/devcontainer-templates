FROM mathworks/matlab

RUN sudo apt-get update && sudo apt-get install -y git

ENV LD_LIBRARY_PATH=/opt/matlab/R2022b/bin/glnxa64

RUN python -m pip install matlabengine
