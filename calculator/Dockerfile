FROM microsoft/dotnet:2.0-sdk AS bld
WORKDIR /app
COPY /src/calculator.csproj /app
RUN dotnet restore
COPY /src /app
RUN dotnet publish -o output

FROM microsoft/dotnet:2.0-runtime
COPY --from=bld /app/output /app
WORKDIR /app
ENV URLOptimizerJobs=http://opt:80/api/Jobs/
ENTRYPOINT ["dotnet", "calculator.dll"]

