FROM quay.io/keycloak/keycloak:20.0.5 as builder

ENV KC_DB=postgres

WORKDIR /opt/keycloak

RUN /opt/keycloak/bin/kc.sh build

FROM quay.io/keycloak/keycloak:20.0.5


COPY --from=builder /opt/keycloak/ /opt/keycloak/
ADD realm-export.json /opt/keycloak/data/import/realm-export.json

ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
CMD ["start", "--import-realm", "--optimized"]
