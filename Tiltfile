# Build
custom_build(
    # Name of the container image
    ref = 'catalog-service',
    # Command to build the container image
    # On Windows, replace $EXPECTED_REF with %EXPECTED_REF%
    command = 'mvn -DskipTests spring-boot:build-image -Dspring-boot.build-image.imageName=%EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(kustomize('k8s'))

# Manage
k8s_resource('catalog-service', port_forwards=['9001'])
