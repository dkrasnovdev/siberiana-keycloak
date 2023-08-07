FROM quay.io/keycloak/keycloak:21.1.2 AS keycloak

WORKDIR /opt/keycloak

COPY ./keycloak/keycloak.conf ./conf/

RUN /opt/keycloak/bin/kc.sh build --features=declarative-user-profile


FROM quay.io/keycloak/keycloak:21.1.2

WORKDIR /opt/keycloak

COPY --from=keycloak /opt/keycloak ./
COPY ./keycloak/siberiana-realm.json ./data/import/

HEALTHCHECK --start-period=5s --interval=5s --timeout=2s \
  CMD curl -fs http://localhost:8080/realms/siberiana/account/ || exit 1

CMD ["start", "--optimized", "--import-realm" ,"--proxy=edge"]
