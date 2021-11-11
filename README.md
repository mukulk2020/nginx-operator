# nginx-operator

helm pull bitnami/nginx
tar zxvf nginx-9.5.13.tgz
mkdir nginx-operator
cd nginx-operator
operator-sdk init --plugins=helm --domain=example.com
operator-sdk create api --version=v1alpha1 --group demo --kind=Nginx --helm-chart=../nginx/
make docker-build docker-push IMG="ocr.hclcnlabs.com/test/nginx-operator:v0.0.1"
