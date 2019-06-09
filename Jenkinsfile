kind: "BuildConfig"
  apiVersion: "v1"
  metadata:
    labels:
      application: test
    name: "test-pipeline"
    namespace: "p2"
  spec:
    source:
      type: Git
      git:
        uri: ${SOURCE_REPOSITORY_URL}
        ref: ${SOURCE_REPOSITORY_REF}
      contextDir: ${CONTEXT_DIR}
    triggers:
    - type: "GitHub"
      github:
        secret: ${GITHUB_WEBHOOK_SECRET}
    - type: "ConfigChange"
    strategy:
      type: "JenkinsPipeline"
      jenkinsPipelineStrategy:
        jenkinsfilePath: ${PIPELINE_SCRIPT}
