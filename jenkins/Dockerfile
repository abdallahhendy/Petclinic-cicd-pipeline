## We'll install the tools automatically from the Dockerfile, No manual installation is needed.

FROM jenkins/jenkins:lts

# Switch to root user to install our desired tools
USER root

RUN apt update && apt install -y \
    git \
    docker.io \
    maven \
    openjdk-17-jdk \
    openssh-client \
    curl


# Install 'trivy' for vulnerability scanning
RUN curl -fsSL https://aquasecurity.github.io/trivy-repo/deb/public.key | tee /usr/share/keyrings/trivy.asc && \
    echo "deb [signed-by=/usr/share/keyrings/trivy.asc] https://aquasecurity.github.io/trivy-repo/deb generic main" | tee /etc/apt/sources.list.d/trivy.list && \
    apt update && apt install -y trivy

USER jenkins