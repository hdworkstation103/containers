FROM runpod/stable-diffusion:web-automatic-1.5.16

SHELL ["/bin/bash", "-c"]

ENV PATH="${PATH}:/workspace/stable-diffusion-webui/venv/bin"

WORKDIR /

RUN rm /workspace/v1-5-pruned-emaonly.ckpt
RUN wget -O model.safetensors https://civitai.com/api/download/models/11811
RUN wget -0 model.vae.pt https://civitai.com/api/download/models/11811?type=VAE&format=Other
RUN pip install -U xformers
RUN pip install runpod

ADD handler.py .
ADD start.sh /start.sh
RUN chmod +x /start.sh

CMD [ "/start.sh" ]
