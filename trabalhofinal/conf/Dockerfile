FROM continuumio/anaconda3:2022.05
LABEL maintainer="sauloandrade"
USER root
SHELL ["/bin/bash", "--login", "-c"]
RUN mkdir -p /opt/fds
RUN git clone https://github.com/sauloaalmeida/FundamentosDataScience.git /opt/fds
RUN conda create -y --quiet --name fdsenv -c anaconda python=3.9.12 anaconda=2022.05 
SHELL ["conda", "run", "-n", "fdsenv", "/bin/bash", "-c"]
RUN conda install jupyter=1.0.0 -y --quiet
EXPOSE 8888
CMD jupyter notebook --notebook-dir=/opt/fds --ip='*' --NotebookApp.token='' --NotebookApp.password='' --port=8888 --no-browser --allow-root
