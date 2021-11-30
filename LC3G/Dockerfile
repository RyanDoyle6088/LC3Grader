# https://docs.docker.com/compose/django/
FROM python:3
ENV PYTHONUNBUFFERED=1
RUN mkdir /code
RUN apt update
RUN apt install -y build-essential flex gcc-multilib tmux
RUN git clone https://github.com/ndragon798/lc3tools.git
WORKDIR /lc3tools
RUN ./configure --installdir /usr/bin
RUN make && make install
WORKDIR /code
RUN chmod +x /code/laser
COPY requirements.txt /code/
RUN pip install -r requirements.txt
COPY . /code/