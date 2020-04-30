node
{
def app

stage('clone repo')
{
checkout scm
}
stage('build image')
{
app=docker.build("995254/dockerizedjenkinspipeline")
}
stage('test image')
{
app.inside{
echo "Tests passed"
}
}
stage('push image')
{
docker.withRegistry('https://registry.hub.docker.com','a347a119-f521-4940-8bbf-1901a5a9e905'){
app.push("${env.BUILD_NUMBER}")
app.push("latest")
}
echo "trying to push docker buid to docker hub"
}
}
