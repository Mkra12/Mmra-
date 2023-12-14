# Mmra-
Mkra@
"annotations": {
  "org.opencontainers.image.description": "My multi-arch image"
}
# This workflow uses actions that are not certified by GitHub.
# They are provided by a third-party and are governed by
# separate terms of service, privacy policy, and support
# documentation.

- name: Build and push Docker image
  uses: docker/build-push-action@f2a1d5e99d037542a71f64918e516c093c6f3fc4
  with:
    context: .
    file: ./Dockerfile
    platforms: ${{ matrix.platforms }}
    push: true
    outputs: type=image,name=target,annotation-index.org.opencontainers.image.description=My multi-arch image
