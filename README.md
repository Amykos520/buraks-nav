import 'dart:core';
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.white70,
        appBar: AppBar(
          backgroundColor: Colors.white70,
          centerTitle: true,
          title: Text('KOMBİN SEÇ', style: TextStyle(fontSize: 16, color: Colors.black)),
        ),
        body: KiyafetSayfasi(),
      ),
    );
  }
}

class KiyafetSayfasi extends StatefulWidget {
  @override
  _KiyafetSayfasiState createState() => _KiyafetSayfasiState();
}

class _KiyafetSayfasiState extends State<KiyafetSayfasi> {
  int ust = 0;
  int pantalon = 0;
  int ayakkabi = 0;

  List<String> ustKiyafetler = [
    'beyaz_kazak',
    'mavi_kazak',
    'siyah_pantolon',
  ];
  List<String> pantalonKiyafetler = [
    'gri_pantolon',
    'gri_pantolon (2)',
    'siyah_kazak',
  ];
  List<String> ayakkabiKiyafetler = [
    'kahverengi_ayakkabı',
    'kırmızı_ayakkabı',
    'mavi_ayakkabı',
  ];

  void kombiniGetir() {
    setState(() {
      ust = Random().nextInt(ustKiyafetler.length);
      pantalon = Random().nextInt(pantalonKiyafetler.length);
      ayakkabi = Random().nextInt(ayakkabiKiyafetler.length);
    });
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: <Widget>[
          Padding(
            padding: const EdgeInsets.all(12.0),
            child: Column(
              children: [
                TextButton(
                  onPressed: kombiniGetir,
                  child: Image.asset(
                    'assets/${ustKiyafetler[ust]}.jpeg',
                    fit: BoxFit.cover,
                    width: 200,

                  ),
                ),
                Text(
                  ustKiyafetler[ust],
                  style: TextStyle(color: Colors.black),
                ),
                SizedBox(height: 5),
                TextButton(
                  onPressed: kombiniGetir,
                  child: Image.asset(
                    'assets/${pantalonKiyafetler[pantalon]}.jpeg',
                    fit: BoxFit.cover,
                    width: 200,

                  ),
                ),
                Text(
                  pantalonKiyafetler[pantalon],
                  style: TextStyle(color: Colors.black),
                ),
                SizedBox(height: 5),
                TextButton(
                  onPressed: kombiniGetir,
                  child: Image.asset(
                    'assets/${ayakkabiKiyafetler[ayakkabi]}.jpeg',
                    fit: BoxFit.cover,
                    width: 200,
                    
                  ),
                ),
                Text(
                  ayakkabiKiyafetler[ayakkabi],
                  style: TextStyle(color: Colors.black),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}
