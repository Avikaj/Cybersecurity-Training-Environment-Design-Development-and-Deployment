FROM ubuntu:20.04

# Install dependencies
RUN apt-get update && apt-get install -y samba

# Copy the Samba configuration file
COPY smb.conf /etc/samba/smb.conf

# Create a directory for shared files
RUN mkdir -p /srv/samba/shared &&     chmod -R 0755 /srv/samba/shared &&     chown -R nobody:nogroup /srv/samba/shared

# Expose Samba ports
EXPOSE 137/udp 138/udp 139/tcp 445/tcp

# Run Samba in the foreground
CMD ["smbd", "--foreground", "--no-process-group"]
