# よく使うコマンド
## docker関連

```
docker build -t saisa6153/cloudroom --rm .
docker run -i -t saisa6153/cloudroom
docker run -d -p 80:80 saisa6153/cloudroom
docker inspect --format '{{ .NetworkSettings.IPAddress }}' xxxxxxx
docker rm $(docker ps -a -q)
docker rmi $(docker images | awk '/^<none>/ { print $3 }')
```

## eb関連

```
brew install aws-elasticbeanstalk
```

# ディレクトリ構成

```
Root
├── Dockerrun.aws.json
├── README.md
├── app
│   ├── Dockerfile
│   └ sampleapp  
~
└── baseimage
    └── Dockerfile
```

# 参考文献
- [EBに上げるメイン](http://flux7.com/blogs/docker/10-steps-deploying-docker-containers-on-elastic-beanstalk/)
- [Dockerrun.aws.json](http://docs.aws.amazon.com/ja_jp/elasticbeanstalk/latest/dg/create_deploy_docker_image.html)
- [Docker EBトラブルシューティング](http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/troubleshooting-docker.html)

## ebextensions
- [.ebextensionsについて](http://www.slideshare.net/hz_ouchi/elastic-beanstalk-31983440)
- [AWS Elastic Beanstalk 環境のカスタマイズと設定](http://docs.aws.amazon.com/ja_jp/elasticbeanstalk/latest/dg/customize-containers.html)
- [Linux を実行する EC2 インスタンス上のソフトウェアのカスタマイズ](http://docs.aws.amazon.com/ja_jp/elasticbeanstalk/latest/dg/customize-containers-ec2.html)
- [環境リソースのカスタマイズ](http://docs.aws.amazon.com/ja_jp/elasticbeanstalk/latest/dg/environment-resources.html)
