import 'package:epay/mainmenu.dart';
import 'package:flutter/material.dart';
/*

Question: Home Page
*/

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      title: 'ePay App',
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.green,
      appBar: AppBar(
        leading: const Icon(
          Icons.close,
          color: Colors.white,
        ),
        backgroundColor: Colors.blue,
        title: const Text(
          'Welcome to ePay',
          style: TextStyle(color: Colors.white),
        ),
      ),
      body: Center(
        child: Column(
          children: [
            const Icon(
              Icons.monetization_on,
              size: 200,
              color: Colors.white,
            ),
            const Text(
              'More Money in Your Pocket',
              style: TextStyle(
                fontSize: 20,
                color: Colors.white,
              ),
            ),
            const SizedBox(height: 15),
            HomePageMenuItem(
              text: 'Main Menu',
              icon: Icons.arrow_forward,
              onTap: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => const MainMenu()),
                );
              },
            ),
            const SizedBox(height: 20),
            const HomePageMenuItem(
              text: 'Check Rates',
              icon: Icons.arrow_forward,
            ),
            const SizedBox(height: 20),
            const HomePageMenuItem(
              text: 'WhatsApp ePay',
              icon: Icons.arrow_forward,
            ),
            const SizedBox(height: 40),
            const Text(
              'Forgot Your Pin?',
              textAlign: TextAlign.center,
            ),
            const Text('Dial *134*542# to Reset it'),
          ],
        ),
      ),
    );
  }
}

class HomePageMenuItem extends StatelessWidget {
  const HomePageMenuItem(
      {super.key, required this.text, required this.icon, this.onTap});

  final String text;
  final IconData icon;
  final VoidCallback? onTap;

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: onTap,
      child: Container(
        decoration: const BoxDecoration(color: Colors.black),
        height: 40,
        width: 250,
        child: Row(
          mainAxisAlignment: MainAxisAlignment.spaceBetween,
          children: [
            Padding(
              padding: const EdgeInsets.only(left: 12.0),
              child: Text(
                text,
                style: const TextStyle(color: Colors.white, fontSize: 18),
              ),
            ),
            Padding(
              padding: const EdgeInsets.only(right: 12.0),
              child: Icon(
                icon,
                size: 20,
                color: Colors.green,
              ),
            ),
          ],
        ),
      ),
    );
  }
}

import 'package:epay/recipients.dart';
import 'package:flutter/material.dart';
import 'package:epay/main.dart';

/*

Question: Main Menu
*/

void main() {
  runApp(const MyApp2());
}

class MyApp2 extends StatelessWidget {
  const MyApp2({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'MainMenu',
      theme: ThemeData(),
      home: const MainMenu(),
    );
  }
}

class MainMenu extends StatelessWidget {
  const MainMenu({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: MenuScreen(),
    );
  }
}

class MenuScreen extends StatelessWidget {
  const MenuScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text(
          "ePay Main Menu",
          style: TextStyle(color: Colors.white),
        ),
        leading: IconButton(
          icon: const Icon(
            Icons.arrow_back_rounded,
            color: Colors.white,
          ), // icon
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => const MyApp()),
            );
          },
        ),
        backgroundColor: Colors.blue,
      ),
      body: Center(
        child: Column(
          children: [
            const SizedBox(height: 20),
            Material(
              elevation: 20,
              child: Container(
                color: Colors.white,
                height: 75,
                width: 510,
                child: ListTile(
                  title: const Padding(
                    padding: EdgeInsets.only(right: 170.0),
                    child: Icon(
                      Icons.group,
                      color: Colors.green,
                      size: 40,
                    ),
                  ),
                  subtitle: const Padding(
                    padding: EdgeInsets.only(left: 80.0),
                    child: Text(
                      'Recipients',
                      style: TextStyle(
                        color: Colors.black,
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                  ),
                  onTap: () {
                    Navigator.push(
                      context,
                      MaterialPageRoute(
                          builder: (context) => const Recipients()),
                    );
                  },
                  trailing: const Padding(
                    padding: EdgeInsets.only(right: 45.0),
                    child: Icon(
                      Icons.arrow_forward,
                      color: Colors.green,
                      size: 30,
                    ),
                  ),
                ),
              ),
            ),
            const SizedBox(height: 30),
            Column(
              children: [
                Material(
                  elevation: 20,
                  child: Container(
                    color: Colors.white,
                    height: 75,
                    width: 510,
                    child: const ListTile(
                      title: Padding(
                        padding: EdgeInsets.only(right: 170.0),
                        child: Icon(
                          Icons.person,
                          color: Colors.green,
                          size: 40,
                        ),
                      ),
                      subtitle: Padding(
                        padding: EdgeInsets.only(left: 80.0),
                        child: Text(
                          'My Profile',
                          style: TextStyle(
                              color: Colors.black, fontWeight: FontWeight.bold),
                        ),
                      ),
                      trailing: Padding(
                        padding: EdgeInsets.only(right: 45.0),
                        child: Icon(
                          Icons.arrow_forward,
                          color: Colors.green,
                          size: 30,
                        ),
                      ),
                    ),
                  ),
                ),
                const SizedBox(height: 30),
                Column(
                  children: [
                    Material(
                      elevation: 30,
                      child: Container(
                        color: Colors.white,
                        height: 75,
                        width: 510,
                        child: const ListTile(
                          title: Padding(
                            padding: EdgeInsets.only(right: 170.0),
                            child: Icon(
                              Icons.phone,
                              color: Colors.green,
                              size: 40,
                            ),
                          ),
                          subtitle: Padding(
                            padding: EdgeInsets.only(left: 80.0),
                            child: Text(
                              'Contact ePay',
                              style: TextStyle(
                                  color: Colors.black,
                                  fontWeight: FontWeight.bold),
                            ),
                          ),
                          trailing: Padding(
                            padding: EdgeInsets.only(right: 45.0),
                            child: Icon(
                              Icons.arrow_forward,
                              color: Colors.green,
                              size: 30,
                            ),
                          ),
                        ),
                      ),
                    ),
                    const SizedBox(height: 30),
                    Column(
                      children: [
                        Material(
                          elevation: 30,
                          child: Container(
                            color: Colors.white,
                            height: 75,
                            width: 510,
                            child: const ListTile(
                              title: Padding(
                                padding: EdgeInsets.only(right: 170.0),
                                child: Icon(
                                  Icons.logout,
                                  color: Colors.green,
                                  size: 40,
                                ),
                              ),
                              subtitle: Padding(
                                padding: EdgeInsets.only(left: 80.0),
                                child: Text(
                                  'Sign Out',
                                  style: TextStyle(
                                      color: Colors.black,
                                      fontWeight: FontWeight.bold),
                                ),
                              ),
                              trailing: Padding(
                                padding: EdgeInsets.only(right: 45.0),
                                child: Icon(
                                  Icons.arrow_forward,
                                  color: Colors.green,
                                  size: 30,
                                ),
                              ),
                            ),
                          ),
                        ),
                      ],
                    ),
                  ],
                ),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

import 'package:flutter/material.dart';
import 'package:epay/mainmenu.dart';

/*

Question: List of Recipients
*/

void main() {
  runApp(const Recipients());
}

class Recipients extends StatelessWidget {
  const Recipients({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: RecipientsHomePage(),
    );
  }
}

class RecipientsHomePage extends StatelessWidget {
  const RecipientsHomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.blue,
        title: const Text(
          "List of Recipients",
          style: TextStyle(color: Colors.white),
        ),
        leading: IconButton(
          icon: const Icon(
            Icons.arrow_back_rounded,
            color: Colors.white,
          ), // icon
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => const MainMenu()),
            );
          },
        ),
      ),
      body: RecipientsList(),
    );
  }
}

class Contacts {
  String names;
  String number;

  Contacts(this.names, this.number);
}

class RecipientsList extends StatelessWidget {
  final List<Contacts> contact = [
    Contacts('John', '078654323'),
    Contacts('Mary', '074654313'),
    Contacts('Jane', '068654323'),
    Contacts('Johnson', '079654323'),
    Contacts('Phillip', '075654323'),
    Contacts('George', '078654323'),
    Contacts('Gerry', '078654323'),
  ];

  RecipientsList({super.key});
  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemCount: contact.length,
      itemBuilder: (context, index) {
        return Column(
          children: [
            const Divider(height: 1, color: Colors.grey),
            ListTile(
              leading: const Icon(
                Icons.person_3_rounded,
                color: Colors.grey,
              ),
              title: Text(contact[index].names),
              subtitle: Text(
                contact[index].number,
                style: const TextStyle(color: Colors.grey),
              ),
              trailing: const Text(
                'Send Money',
                style: TextStyle(fontSize: 14),
              ),
            ),
          ],
        );
      },
    );
  }
}



