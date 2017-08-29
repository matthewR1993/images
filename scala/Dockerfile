FROM  openjdk:8u141-jdk

ENV SCALA_VERSION 2.12.3
ENV SBT_VERSION 0.13.16

RUN touch /usr/lib/jvm/java-8-openjdk-amd64/release

# Install Scala if needed
#RUN \
#  curl -fsL https://downloads.typesafe.com/scala/$SCALA_VERSION/scala-$SCALA_VERSION.tgz | tar xfz - -C /root/ && \
#  echo >> /root/.bashrc && \
#  echo 'export PATH=~/scala-$SCALA_VERSION/bin:$PATH' >> /root/.bashrc

# Install sbt if you need to build jar
#RUN \
#  curl -L -o sbt-$SBT_VERSION.deb https://dl.bintray.com/sbt/debian/sbt-$SBT_VERSION.deb && \
#  dpkg -i sbt-$SBT_VERSION.deb && \
#  rm sbt-$SBT_VERSION.deb && \
#  apt-get update && \
#  apt-get install sbt && \
#  sbt sbtVersion

# optoinally assemble during image build
# RUN sbt assembly

ENV PROJ_NAME akka-bazz
ENV JAR_NAME $PROJ_NAME-assembly-1.0.jar

# Copy jar file
ADD /target/scala-2.12/$JAR_NAME /root/source/$JAR_NAME

WORKDIR /root/source/
RUN chmod +x $JAR_NAME

EXPOSE 8080

ENTRYPOINT exec java $JAVA_OPTS -jar $JAR_NAME

