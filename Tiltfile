# Build
custom_build(
    # Name of container image
    ref = 'edge-service',
    # Command to build container image
    command = 'gradlew.bat bootBuildImage --imageName %EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(kustomize('k8s'))

# Manage
k8s_resource('edge-service', port_forwards=['9000'])