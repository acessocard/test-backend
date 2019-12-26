#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see http://aka.ms/containercompat 

FROM microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM microsoft/dotnet:2.2-sdk-nanoserver-1803 AS build
WORKDIR /src
COPY Src/TesteBackendAcesso.API/TesteBackendAcesso.API.csproj Src/TesteBackendAcesso.API/
RUN dotnet restore Src/TesteBackendAcesso.API/TesteBackendAcesso.API.csproj
COPY . .
WORKDIR /src/Src/TesteBackendAcesso.API
RUN dotnet build TesteBackendAcesso.API.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish TesteBackendAcesso.API.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "TesteBackendAcesso.API.dll"]
