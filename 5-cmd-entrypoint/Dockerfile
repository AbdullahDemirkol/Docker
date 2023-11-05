FROM ubuntu:18.04

# CMD komutu dışarıdan override edilebilirdir. Fakat bir komutu göndermeden sadece değer ile uyumasını sağlamak istersek ENTRYPOINT komutunu kullanırız.
ENTRYPOINT [ "sleep" ]
# Eğer bir değer gönderilmez ise default value olarak 2 saniye uyumasını sağlamak için CMD komutundan yardım alırız.
CMD [ "2" ]

# CMD ["sleep","4"]
# CMD sleep 4