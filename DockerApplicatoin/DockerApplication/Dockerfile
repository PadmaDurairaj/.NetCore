FROM mcr.microsoft.com/dotnet/core/aspnet:3.0 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/core/sdk:3.0 AS build
WORKDIR /src
COPY ["DockerApplication.csproj", "./"]
RUN dotnet restore "./DockerApplication.csproj"
COPY . .
RUN dotnet build "DockerApplication.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "DockerApplication.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "DockerApplication.dll"]