---
layout: post
title: "Elastic Search 설치"
description: "Elastic Search 설치하기"
categories: [etc]
tags: [elasticsearch, elastic]
redirect_from:
  - /2018/09/28/
---

# 일단 설치를 한다.

    weget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.4.1.rpm
    rpm -i elasticsearch-6.4.1.rpm
    systemctl enable elasticsearch.service
    service elasticsearch start
    service elasticsearch stop
    curl -XGET localhost:9200

# 오류가 날 경우 확인 후 다시 실행
    # systemcctl status elasticsearch
    # service elasticsearch stop
    # service elasticsearch start
    # curl -XGET localhost:9200



# 방화벽 풀어주고 설정 후 다시 확인
    vim /etc/elasticsearch/elasticsearch.yml
    network.host: 0.0.0.0 으로 변경
    curl -XGET localhost:9200
    {
      "name" : "rUJc9OZ",
      "cluster_name" : "elasticsearch",
      "cluster_uuid" : "hGDwjwfRSi-U8G858zWs3g",
      "version" : {
        "number" : "6.4.1",
        "build_flavor" : "default",
        "build_type" : "rpm",
        "build_hash" : "e36acdb",
        "build_date" : "2018-09-13T22:18:07.696808Z",
        "build_snapshot" : false,
        "lucene_version" : "7.4.0",
        "minimum_wire_compatibility_version" : "5.6.0",
        "minimum_index_compatibility_version" : "5.0.0"
      },
      "tagline" : "You Know, for Search"
    }

 끝