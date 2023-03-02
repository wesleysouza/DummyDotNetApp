FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
COPY . . /app
WORKDIR /app
EXPOSE 80/tcp

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS publish

WORKDIR /app
COPY DummyDotNetApp.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o dist


ENV _="dsdasdasdsad"
ENV asdsad="DDDDDD"
ENV jose="wesley"

FROM base AS final
WORKDIR /dist
COPY AppDynamicsConfig.json .
COPY --from=publish /app/dist .
ENTRYPOINT ["dotnet", "DummyDotNetApp.dll"]
