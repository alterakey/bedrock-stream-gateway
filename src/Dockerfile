FROM public.ecr.aws/docker/library/python:3.12.0-slim-bullseye
COPY --from=public.ecr.aws/awsguru/aws-lambda-adapter:0.9.0 /lambda-adapter /opt/extensions/

WORKDIR /app
COPY . .

RUN pip3 install -r requirements.txt -U --no-cache-dir

ENV AWS_LWA_INVOKE_MODE=RESPONSE_STREAM
ENV PORT=8000
CMD [ "python3", "-m", "api.app" ]