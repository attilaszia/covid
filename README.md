# covid

```
                                    {
                                        key: "getVaccinedetails",
                                        value: function () {
                                            return this.vaccineDetails;
                                        },
                                    },
                                    {
                                        key: "setVaccineDetails",
                                        value: function (e) {
                                            this.vaccineDetails = e;
                                        },
                                    },
                                    {
                                        key: "decodeToken",
                                        value: function () {
                                            var e = this;
                                            if (null !== this.encryptedToken) {
                                                var t = JSON.parse(JSON.stringify(a.decode(this.encryptedToken)));
                                                if ("888888880" === t.id) return this.setVaccineDetails(t), this.navCtrl.navigateForward("vaccine-details"), void this.refreshPublicKey();
                                                this.fileService.fileRead().then(function (t) {
                                                    a.verify(e.encryptedToken, t.data, function (t, n) {
                                                        t
                                                            ? (e.setVaccineDetails(null), e.navCtrl.navigateForward("invalid-qr-code"), e.refreshPublicKey())
                                                            : (e.setVaccineDetails(n), e.navCtrl.navigateForward("vaccine-details"), e.refreshPublicKey());
                                                    });
                                                });
                                            }
                                        },
                                    },

```
