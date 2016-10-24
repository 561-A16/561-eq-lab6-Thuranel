FROM ymazieres/dotnet:compile

WORKDIR /src/tests

ENV ASPNETCORE_URLS http://+:5000

CMD ["sh", "../../script/run.sh"]
COPY /Docker/run.sh /script/run.sh
RUN chmod +x ../../script/run.sh

COPY /src /src

#pour builder l'image
#docker build -t webapp -f ./Docker/Dockerfile .

#pour executer l'image
#docker run -it --rm -v $PWD/packages:/root/.nuget/packages -p 8080:5000 webapp