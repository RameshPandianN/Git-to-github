node
{
def app

stage('clone repo')
{
checkout scm
}
stage('build image')
{
app=docker.build("995252/Dockerizedpipeline")
}
stage('test image')
{
app.inside{
echo "Tests passed"
}
stage('push image')
{
docker.withRegistry('https://registry.hub.docker.com','docker-hub'){
app.push("$(env.BUILD_NUMBER}")
app.push("latest")
}
echo "trying to push docker buid to docker hub"
}
