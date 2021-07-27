FROM kong:2.1

# Build time defaults
ARG build_KONG_DATABASE=off
ARG build_KONG_PLUGINS=request-transformer,cors,key-auth
ARG build_KONG_DECLARATIVE_CONFIG=/var/lib/kong/kong.yml
ARG build_SUPABASE_ANON_KEY
ARG build_SUPABASE_SERVICE_ROLE_KEY

# Run time values
ENV KONG_DATABASE=$build_KONG_DATABASE
ENV KONG_PLUGINS=$build_KONG_PLUGINS
ENV KONG_DECLARATIVE_CONFIG=$build_KONG_DECLARATIVE_CONFIG

USER root
COPY kong.yml /var/lib/kong/kong.yml
RUN sed -i "s/SUPABASE_ANON_KEY/$build_SUPABASE_ANON_KEY/g" /var/lib/kong/kong.yml
RUN sed -i "s/SUPABASE_SERVICE_ROLE_KEY/$build_SUPABASE_SERVICE_ROLE_KEY/g" /var/lib/kong/kong.yml
