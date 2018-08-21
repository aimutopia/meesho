CREATE TABLE client_requests(
  uuid UUID PRIMARY KEY,
  request_type TEXT NOT NULL,
  status ENUM NOT NULL,
  status_update_timestamp TIMESTAMP NOT NULL
);

CREATE TABLE communication_status(
 uuid UUID PRIMARY KEY,
 client_request_uuid UUID NOT NULL references client_requests(uuid),
 status ENUM NOT NULL,
 status_update_timestamp TIMESTAMP NOT NULL,
 recipient_uuid text NOT NULL
);

CREATE TABLE communication_channel_requests(
 uuid UUID PRIMARY KEY,
 communication_uuid UUID NOT NULL references  communication_status(uuid),
 channel text not null,
 init_timestamp TIMESTAMP NOT NULL,
 status ENUM NOT NULL,
 status_update_timestamp TIMESTAMP NOT NULL
);

CREATE TABLE vendor_requests(
uuid UUID PRIMARY KEY,
vendor text NOT NULL,
recipient_endpoint text NOT NULL,
communication_channel_request_uuid UUID NOT NULL references communication_channel_requests(uuid),
status ENUM NOT NULL,
status_update_timestamp TIMESTAMP NOT NULL
);
