# Build
custom_build(
    # Name of the container image
    ref = 'config-service',
    # Command to build the container image
    # On Windows, replace $EXPECTED_REF with %EXPECTED_REF%
    command = '	./mvnw spring-boot:build-image -DskipTests   -Dspring-boot.build-image.imageName=$EXPECTED_REF',
    # Files to watch that trigger a new build
    deps = ['src']
)

# Deploy
k8s_yaml(kustomize('k8s'))

# Manage
k8s_resource('config-service', port_forwards=['8888'])