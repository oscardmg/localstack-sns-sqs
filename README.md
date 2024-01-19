https://medium.com/@anchan.ashwithabg95/using-localstack-sns-and-sqs-for-devbox-testing-fa09de5e3bbb

docker-compose up -d

curl http://localhost:4566


aws configure set aws_access_key_id "dummy" --profile localstack
aws configure set aws_secret_access_key "dummy" --profile localstack
aws configure set region "us-east-1" --profile localstack
aws configure set output "table" --profile localstack


aws --endpoint-url=http://localhost:4566 sns create-topic --name order-creation-events --region us-east-1 --profile localstack --output table | cat
aws --endpoint-url=http://localhost:4566 sns create-topic --name signals-hub-develop-sns --region us-east-1 --profile localstack --output table | cat



 {
    endpoint: 'http://localhost:4566',
    region:  'us-east-1',
  }