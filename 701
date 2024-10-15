<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title> Öğrenci Bilgi Sistemi - Güncel</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
            color: #2C3E50;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            min-height: 100vh;
            box-sizing: border-box;
        }

        .container {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 90%;
            box-sizing: border-box;
            overflow: hidden;
        }

        h1 {
            color: #2C3E50;
            font-size: 24px;
            margin-bottom: 15px;
        }

        input[type="text"] {
            padding: 12px;
            font-size: 16px;
            width: 100%;
            max-width: 100%;
            margin-bottom: 15px;
            border: 1px solid #cccccc;
            border-radius: 6px;
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.05);
            box-sizing: border-box;
        }

        button {
            padding: 12px;
            font-size: 16px;
            background-color: #F39C12;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            width: 100%;
            max-width: 100%;
        }

        button:hover {
            background-color: #e67e22;
        }

        .result-table {
            margin-top: 20px;
            width: 100%;
            border-collapse: collapse;
            border: 1px solid #eeeeee;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            border-radius: 6px;
            table-layout: auto; 
            word-wrap: break-word;
            overflow: hidden;
        }

        .result-table th, .result-table td {
            padding: 8px;
            text-align: center;
            font-size: 14px;
            height: 45px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .result-table th {
            background-color: #2C3E50;
            color: white;
            font-weight: 600;
        }

        .result-table tr:nth-child(even) {
            background-color: #f9f9f9;
        }

        .category {
            background-color: #ecf0f1;
            font-weight: bold;
            white-space: normal;
        }

        .total-row td {
            background-color: #2C3E50;
            color: white;
            font-weight: bold;
        }

        .footer {
            margin-top: 20px;
            font-size: 12px;
            color: #95a5a6;
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 22px;
            }
            button, input[type="text"] {
                font-size: 14px;
                padding: 10px;
            }
            .result-table th, .result-table td {
                font-size: 12px;
                padding: 6px;
            }
            .container {
                padding: 15px;
            }
        }

        .result-table .topic-column {
            width: 40%;
        }

        .result-table .small-column {
            width: 20%;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
</head>
<body>
    <div class="container">
        <h1> Öğrenci Bilgi Sistemi</h1>
        <p>Lütfen TC Kimlik Numaranızı Giriniz:</p>

        <input type="text" id="tcInput" placeholder="TC Kimlik Numarası">
        <br>
        <button onclick="fetchStudentData()">Sonuçları Gör</button>

        <div id="studentData" class="result"></div>

        <div class="footer">
            <p>© 2024 OG Öğrenci Bilgi Sistemi. Tüm Hakları Saklıdır.</p>
        </div>
    </div>

    <script>
        const studentData = {
            "29404922978": {
                "name": "ADA KOCA",
                "ranking": 1,
                "lgs_score": 423.403,
                "subjects": {
                    "TÜRKÇE": {"doğru": 18, "yanlış": 2, "net": 17.33},
                    "MATEMATİK": {"doğru": 11, "yanlış": 5, "net": 9.33},
                    "FEN BİLİMLERİ": {"doğru": 18, "yanlış": 1, "net": 17.67},
                    "İNKILAP TARİHİ": {"doğru": 9, "yanlış": 1, "net": 8.67},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "İNGİLİZCE": {"doğru": 10, "yanlış": 0, "net": 10.0}
                },
                "totals": {"doğru": 74, "yanlış": 11, "net": 70.33}
            },
            "35165377940": {
                "name": "HAZAL AYDIN",
                "ranking": 2,
                "lgs_score": 406.48,
                "subjects": {
                    "TÜRKÇE": {"doğru": 17, "yanlış": 3, "net": 16.0},
                    "MATEMATİK": {"doğru": 10, "yanlış": 5, "net": 8.33},
                    "FEN BİLİMLERİ": {"doğru": 18, "yanlış": 2, "net": 17.33},
                    "İNKILAP TARİHİ": {"doğru": 9, "yanlış": 1, "net": 8.67},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 1, "net": 7.67},
                    "İNGİLİZCE": {"doğru": 7, "yanlış": 3, "net": 6.0}
                },
                "totals": {"doğru": 69, "yanlış": 15, "net": 64.0}
            },
            "70771196288": {
                "name": "ÇAĞAN TURGUT",
                "ranking": 3,
                "lgs_score": 401.198,
                "subjects": {
                    "TÜRKÇE": {"doğru": 17, "yanlış": 3, "net": 16.0},
                    "MATEMATİK": {"doğru": 10, "yanlış": 5, "net": 8.33},
                    "FEN BİLİMLERİ": {"doğru": 17, "yanlış": 3, "net": 16.0},
                    "İNKILAP TARİHİ": {"doğru": 9, "yanlış": 0, "net": 8.67},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "İNGİLİZCE": {"doğru": 7, "yanlış": 2, "net": 6.33}
                },
                "totals": {"doğru": 68, "yanlış": 15, "net": 62.66}
            },
            "32809952020": {
                "name": "HAZAL",
                "ranking": 4,
                "lgs_score": 400.862,
                "subjects": {
                    "TÜRKÇE": {"doğru": 19, "yanlış": 0, "net": 19.0},
                    "MATEMATİK": {"doğru": 7, "yanlış": 3, "net": 6.0},
                    "FEN BİLİMLERİ": {"doğru": 15, "yanlış": 5, "net": 13.33},
                    "İNKILAP TARİHİ": {"doğru": 10, "yanlış": 0, "net": 10.0},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 1, "net": 7.67},
                    "İNGİLİZCE": {"doğru": 10, "yanlış": 0, "net": 10.0}
                },
                "totals": {"doğru": 69, "yanlış": 9, "net": 66.0}
            },
            "34262408076": {
                "name": "ÖYKÜNAZ GÖRCEĞİZ",
                "ranking": 5,
                "lgs_score": 379.558,
                "subjects": {
                    "TÜRKÇE": {"doğru": 17, "yanlış": 3, "net": 16.0},
                    "MATEMATİK": {"doğru": 8, "yanlış": 12, "net": 4.0},
                    "FEN BİLİMLERİ": {"doğru": 18, "yanlış": 2, "net": 17.33},
                    "İNKILAP TARİHİ": {"doğru": 10, "yanlış": 0, "net": 10.0},
                    "DİN KÜLTÜRÜ": {"doğru": 7, "yanlış": 3, "net": 6.0},
                    "İNGİLİZCE": {"doğru": 4, "yanlış": 6, "net": 2.0}
                },
                "totals": {"doğru": 64, "yanlış": 26, "net": 55.33}
            },
            "72064153176": {
                "name": "TUNA DEMİR",
                "ranking": 6,
                "lgs_score": 372.141,
                "subjects": {
                    "TÜRKÇE": {"doğru": 16, "yanlış": 4, "net": 14.67},
                    "MATEMATİK": {"doğru": 8, "yanlış": 8, "net": 5.33},
                    "FEN BİLİMLERİ": {"doğru": 14, "yanlış": 6, "net": 12.0},
                    "İNKILAP TARİHİ": {"doğru": 10, "yanlış": 0, "net": 10.0},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "İNGİLİZCE": {"doğru": 9, "yanlış": 1, "net": 8.67}
                },
                "totals": {"doğru": 65, "yanlış": 21, "net": 58.0}
            },
            "13850483282": {
                "name": "EŞLEM SARE ERTEM",
                "ranking": 7,
                "lgs_score": 361.318,
                "subjects": {
                    "TÜRKÇE": {"doğru": 13, "yanlış": 7, "net": 10.67},
                    "MATEMATİK": {"doğru": 7, "yanlış": 10, "net": 3.67},
                    "FEN BİLİMLERİ": {"doğru": 18, "yanlış": 2, "net": 17.33},
                    "İNKILAP TARİHİ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "DİN KÜLTÜRÜ": {"doğru": 6, "yanlış": 4, "net": 4.67},
                    "İNGİLİZCE": {"doğru": 10, "yanlış": 0, "net": 10.0}
                },
                "totals": {"doğru": 62, "yanlış": 25, "net": 53.67}
            },
            "69730230910": {
                "name": "ECE GÖRGÜLÜ",
                "ranking": 8,
                "lgs_score": 356.612,
                "subjects": {
                    "TÜRKÇE": {"doğru": 14, "yanlış": 6, "net": 12.0},
                    "MATEMATİK": {"doğru": 5, "yanlış": 4, "net": 3.67},
                    "FEN BİLİMLERİ": {"doğru": 15, "yanlış": 5, "net": 13.33},
                    "İNKILAP TARİHİ": {"doğru": 10, "yanlış": 0, "net": 10.0},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "İNGİLİZCE": {"doğru": 8, "yanlış": 2, "net": 7.33}
                },
                "totals": {"doğru": 60, "yanlış": 19, "net": 53.66}
            },
            "32761953646": {
                "name": "AYAZ AYDIN",
                "ranking": 9,
                "lgs_score": 350.556,
                "subjects": {
                    "TÜRKÇE": {"doğru": 12, "yanlış": 6, "net": 10.0},
                    "MATEMATİK": {"doğru": 6, "yanlış": 8, "net": 3.33},
                    "FEN BİLİMLERİ": {"doğru": 18, "yanlış": 2, "net": 17.33},
                    "İNKILAP TARİHİ": {"doğru": 7, "yanlış": 2, "net": 6.33},
                    "DİN KÜLTÜRÜ": {"doğru": 8, "yanlış": 1, "net": 7.67},
                    "İNGİLİZCE": {"doğru": 5, "yanlış": 5, "net": 3.33}
                },
                "totals": {"doğru": 56, "yanlış": 24, "net": 47.99}
            },
            "20648357724": {
                "name": "ELA ÇALIŞ",
                "ranking": 10,
                "lgs_score": 342.402,
                "subjects": {
                    "TÜRKÇE": {"doğru": 17, "yanlış": 3, "net": 16.0},
                    "MATEMATİK": {"doğru": 2, "yanlış": 5, "net": 0.33},
                    "FEN BİLİMLERİ": {"doğru": 13, "yanlış": 5, "net": 11.33},
                    "İNKILAP TARİHİ": {"doğru": 8, "yanlış": 2, "net": 7.33},
                    "DİN KÜLTÜRÜ": {"doğru": 6, "yanlış": 4, "net": 4.67},
                    "İNGİLİZCE": {"doğru": 9, "yanlış": 1, "net": 8.67}
                },
                "totals": {"doğru": 55, "yanlış": 20, "net": 48.33}
            },
            "70474206178": {
                "name": "BİLGE DOĞAN",
                "ranking": 11,
                "lgs_score": 327.097,
                "subjects": {
                    "TÜRKÇE": {"doğru": 17, "yanlış": 2, "net": 16.33},
                    "MATEMATİK": {"doğru": 5, "yanlış": 8, "net": 2.33},
                    "FEN BİLİMLERİ": {"doğru": 9, "yanlış": 7, "net": 6.67},
                    "İNKILAP TARİHİ": {"doğru": 7, "yanlış": 1, "net": 6.67},
                    "DİN KÜLTÜRÜ": {"doğru": 6, "yanlış": 4, "net": 4.67},
                    "İNGİLİZCE": {"doğru": 5, "yanlış": 2, "net": 4.33}
                },
                "totals": {"doğru": 49, "yanlış": 24, "net": 41.0}
            },
            "11111111111": {
                "name": "AYSİMA SELEN BELEK",
                "ranking": 12,
                "lgs_score": 319.527,
                "subjects": {
                    "TÜRKÇE": {"doğru": 13, "yanlış": 6, "net": 11.0},
                    "MATEMATİK": {"doğru": 4, "yanlış": 8, "net": 1.33},
                    "FEN BİLİMLERİ": {"doğru": 12, "yanlış": 8, "net": 9.33},
                    "İNKILAP TARİHİ": {"doğru": 9, "yanlış": 0, "net": 9.0},
                    "DİN KÜLTÜRÜ": {"doğru": 7, "yanlış": 2, "net": 6.33},
                    "İNGİLİZCE": {"doğru": 6, "yanlış": 2, "net": 5.33}
                },
                "totals": {"doğru": 51, "yanlış": 26, "net": 42.32}
            }
        };

        function fetchStudentData() {
            const tcNumber = document.getElementById("tcInput").value;
            const data = studentData[tcNumber];
            
            if (data) {
                let subjectRows = '';
                const subjectOrder = ["TÜRKÇE", "MATEMATİK", "FEN BİLİMLERİ", "İNKILAP TARİHİ", "DİN KÜLTÜRÜ", "İNGİLİZCE"];
                for (let subject of subjectOrder) {
                    subjectRows += `
                        <tr>
                            <td class="category topic-column">${subject}</td>
                            <td class="small-column">${data.subjects[subject]["doğru"]}</td>
                            <td class="small-column">${data.subjects[subject]["yanlış"]}</td>
                            <td class="small-column">${data.subjects[subject]["net"]}</td>
                        </tr>
                    `;
                }

                document.getElementById("studentData").innerHTML = `
                    <table class="result-table">
                        <tr>
                            <th colspan="3">Adı: ${data.name}</th>
                            <th>Sıralama: ${data.ranking}</th>
                        </tr>
                        <tr>
                            <td colspan="4">LGS Puanı: ${data.lgs_score}</td>
                        </tr>
                        <tr class="category">
                            <th class="topic-column">Konu</th>
                            <th class="small-column">Doğru</th>
                            <th class="small-column">Yanlış</th>
                            <th class="small-column">Net</th>
                        </tr>
                        ${subjectRows}
                        <tr class="total-row">
                            <td>TOPLAM</td>
                            <td>${data.totals["doğru"]}</td>
                            <td>${data.totals["yanlış"]}</td>
                            <td>${data.totals["net"]}</td>
                        </tr>
                    </table>
                `;
            } else {
                document.getElementById("studentData").innerHTML = "<p>Öğrenci bulunamadı.</p>";
            }
        }
    </script>
</body>
</html>
