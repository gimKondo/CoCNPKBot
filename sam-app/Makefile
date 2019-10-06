S3_BUCKET_NAME = cocnpk-lambda
STACK_NAME = cocnpk

test:
	python -m pytest tests/ -v
package:
	sam validate
	sam package --template-file template.yaml --s3-bucket $(S3_BUCKET_NAME) --output-template-file packaged.yaml
deploy:
	sam validate
	sam package --template-file template.yaml --s3-bucket $(S3_BUCKET_NAME) --output-template-file packaged.yaml
	sam deploy --template-file packaged.yaml --stack-name $(STACK_NAME) --capabilities CAPABILITY_IAM
clean:
	aws cloudformation delete-stack --stack-name $(STACK_NAME)
info:
	aws cloudformation describe-stacks \
    --stack-name $(STACK_NAME) \
    --query 'Stacks[].Outputs[?OutputKey==`CocNPKApi`]' \
    --output table