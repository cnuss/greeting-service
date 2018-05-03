# greeting-service
Sample RESTful Service

# Building (Locally)
 1. `./gradlew installDist`

# Building (Container)
 1. After Building (Locally)
 1. `docker build --tag=cnuss/greeting-service:0.1.0 .`

# Running (Locally)
 1. After Building (Locally)
 1. `build/install/greeting-service/bin/greeting-service`

# Running (Within Container)
 1. After Building (Container)
 1. `docker run --rm -p 11223:11223 cnuss/greeting-service:0.1.0`

# Pushing (Container)
1. After Building (Container)
2. `docker push cnuss/greeting-service:0.1.0`

# Connecting
 1. http://localhost:11223/greeting
 1. http://localhost:11223/greeting?name=Christian

# Kubernetes

## Running on Kubernetes on AWS
This will provision an ELB
1. `kubectl apply -f k8s/deployment.yml`
2. Get the ELB name from the `EXTERNAL-IP` column of `kubectl get services -o wide`
3. http://abcdef-1234.us-west-2.elb.amazonaws.com/greeting
