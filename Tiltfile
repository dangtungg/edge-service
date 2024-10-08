# Build
custom_build(
    # Name of the container image
    ref = 'ghcr.io/dangtungg/edge-service',
    # Command to build the container image
    # On Windows, replace $EXPECTED_REF with %EXPECTED_REF%
    command = './gradlew bootBuildImage --imageName $EXPECTED_REF',
    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yaml', 'k8s/service.yaml', 'k8s/ingress.yaml'])

# Manage
# k8s_resource('edge-service', port_forwards=['9009'])