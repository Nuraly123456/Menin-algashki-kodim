# two_sabak

import 'package:flutter/material.dart';

void main() {
  runApp(CoffeeMenuApp());
}

class CoffeeMenuApp extends StatelessWidget {
  const CoffeeMenuApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primarySwatch: Colors.brown,
        scaffoldBackgroundColor: Colors.white,
      ),
      home: CoffeeMenuScreen(),
    );
  }
}

class CoffeeMenuScreen extends StatelessWidget {
  final List<Map<String, String>> coffeeList = [
    {'name': 'Latte', 'price': '₸1190 / ₸1390', 'image': 'https://images.ctfassets.net/0e6jqcgsrcye/6Dnzkf1ylG7IxDRG9Ez1Ia/0db4f0be1ff6199ae89afa4a0ae26687/How_to_make_a_perfect_cappuccino_at_home.jpg'},
    {'name': 'Espresso', 'price': '₸790', 'image': 'https://sumatocoffee.com/cdn/shop/articles/espresso.png?v=1718370919&width=640'},
    {'name': 'Cappuccino', 'price': '₸890 / ₸1190 / ₸1290', 'image': 'https://media01.stockfood.com/largepreviews/MzQyMzQ4ODcy/11043512-Cappuccino-with-heart.jpg'},
    {'name': 'Americano', 'price': '₸790 / ₸890 / ₸1190', 'image': 'https://majestycoffee.com/cdn/shop/articles/americano_b74a8154-454b-4f74-9a6c-95fbc4152ed3.jpg?v=1684048195'},
    {'name': 'Cartado', 'price': '₸1190', 'image': 'https://coffeepedia.ru/wp-content/uploads/2015/04/Kortado.jpg'},
    {'name': 'Afagatto', 'price': '₸1490', 'image': 'https://static.wixstatic.com/media/6a3e8d_23b343395c7c47feab983d124cc9b4ce~mv2.jpg/v1/fill/w_568,h_770,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/6a3e8d_23b343395c7c47feab983d124cc9b4ce~mv2.jpg'},
    {'name': 'Batch', 'price': '₸890', 'image': 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQMqxstDjXy3s7ga6I4QzfZIfJGqd4FbiAxuQ&s'},
    {'name': 'Maccachino', 'price': '₸1190 / ₸1390', 'image': 'https://www.cafescandelas.com/uploads/media_items/mocaccino-500.500.500.s.jpg'},
    {'name': 'Raf', 'price': '₸1190 / ₸1390', 'image': 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Rafcoffe.jpg'},
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.brown,
        title: Text('Urbo Aksay', style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold, color: Colors.white)),
        centerTitle: true,
      ),
      body: Stack(
        children: [
          // Фон ретінде бірінші суретті қойдық
          Positioned.fill(
            child: Image.network(
              'https://cachizer1.2gis.com/reviews-photos/9ae6fd25-122e-4820-9ced-e65d63a3f848.jpg?w=1920',
              fit: BoxFit.cover,
            ),
          ),
          // Контенттің үстіне орналасқан компоненттер
          Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              crossAxisAlignment: CrossAxisAlignment.center,
              children: [
                // "Ozimizdin orginal - Urbo" жазуы мен сурет ең алдымен
                Padding(
                  padding: const EdgeInsets.all(8.0),
                  child: Row(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                      // Жазуды қосу
                      Text(
                        'Ozimizdin orginal - Urbo',
                        style: TextStyle(
                          fontSize: 20,
                          fontWeight: FontWeight.bold,
                          color: Colors.white,
                        ),
                      ),
                      SizedBox(width: 10),
                      // Суретті қосу
                      Image.network(
                        'https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/46/39/3e/46393e23-948e-b03c-16ab-b4758f9e91fd/AppIcon-0-0-1x_U007emarketing-0-6-0-85-220.png/256x256bb.jpg',
                        width: 100,
                        height: 100,
                      ),
                    ],
                  ),
                ),
                SizedBox(height: 10),
                // Енді "Stol brondau" жазуын көрсетеміз
                Container(
                  padding: EdgeInsets.all(8),
                  decoration: BoxDecoration(
                    borderRadius: BorderRadius.circular(8),
                  ),
                  child: Text(
                    'Stol brondau',
                    style: TextStyle(
                      fontSize: 22,
                      fontWeight: FontWeight.bold,
                      color: Colors.white,
                    ),
                  ),
                ),
                SizedBox(height: 10),
                // Urbo Coffee Menu Button
                ElevatedButton(
                  onPressed: () {
                    Navigator.push(
                      context,
                      MaterialPageRoute(
                        builder: (context) => CoffeeListScreen(coffeeList: coffeeList),
                      ),
                    );
                  },
                  style: ElevatedButton.styleFrom(
                    backgroundColor: Colors.brown,
                    padding: EdgeInsets.symmetric(vertical: 12, horizontal: 24),
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(10),
                    ),
                  ),
                  child: Text('Urbo Menu', style: TextStyle(fontSize: 18, color: Colors.white)),
                ),
                SizedBox(height: 10),
                // Bonus Button
                ElevatedButton(
                  onPressed: () {
                    Navigator.push(
                      context,
                      MaterialPageRoute(
                        builder: (context) => BonusScreen(),
                      ),
                    );
                  },
                  style: ElevatedButton.styleFrom(
                    backgroundColor: Colors.brown,
                    padding: EdgeInsets.symmetric(vertical: 12, horizontal: 24),
                    shape: RoundedRectangleBorder(
                      borderRadius: BorderRadius.circular(10),
                    ),
                  ),
                  child: Text('Bonus', style: TextStyle(fontSize: 18, color: Colors.white)),
                ),
              ],
            ),
          ),
          // Фонды қосымша суретті төменгі жағына қою
          Positioned(
            bottom: 10,
            left: 0,
            right: 0,
            child: Image.network(
              'https://img.postershop.me/21526/7bc15092-3f28-44ce-8ddc-d225f29c7b91_image.png',
              fit: BoxFit.cover,
              height: 120, // Бейненің биіктігі
            ),
          ),
        ],
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          // Show a dialog for location or clone message
          showDialog(
            context: context,
            builder: (context) => AlertDialog(
              title: Text('Location/Clone'),
              content: Column(
                mainAxisSize: MainAxisSize.min,
                children: [
                  Text('Location: Urbo Aksay'),
                  SizedBox(height: 10),
                  Text('Clone: QR Code payment is available'),
                ],
              ),
              actions: [
                TextButton(
                  onPressed: () => Navigator.pop(context),
                  child: Text('Close'),
                ),
              ],
            ),
          );
        },
        backgroundColor: Colors.brown,
        child: Icon(Icons.location_on), // Icon for the location button
      ),
    );
  }
}

class CoffeeListScreen extends StatelessWidget {
  final List<Map<String, String>> coffeeList;

  CoffeeListScreen({required this.coffeeList});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.brown,
        title: Text('Кофе менюсі', style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold, color: Colors.white)),
        centerTitle: true,
      ),
      body: ListView.builder(
        itemCount: coffeeList.length,
        itemBuilder: (context, index) {
          final coffee = coffeeList[index];
          return Card(
            margin: EdgeInsets.all(10),
            shape: RoundedRectangleBorder(
              borderRadius: BorderRadius.circular(15),
            ),
            elevation: 5,
            child: ListTile(
              contentPadding: EdgeInsets.all(10),
              leading: ClipRRect(
                borderRadius: BorderRadius.circular(10),
                child: Image.network(
                  coffee['image']!,
                  width: 60,
                  height: 60,
                  fit: BoxFit.cover,
                  errorBuilder: (context, error, stackTrace) {
                    return Icon(Icons.local_cafe, size: 60, color: Colors.brown);
                  },
                ),
              ),
              title: Text(
                coffee['name']!,
                style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
              ),
              subtitle: Text(
                coffee['price']!,
                style: TextStyle(fontSize: 16, color: Colors.brown[700]),
              ),
              trailing: ElevatedButton(
                onPressed: () {
                  showDialog(
                    context: context,
                    builder: (context) => AlertDialog(
                      title: Text('Төлем'),
                      content: Column(
                        mainAxisSize: MainAxisSize.min,
                        children: [
                          Text('URBO coffee QR КОД АРҚЫЛЫ ТӨЛЕУДІ ҰСЫНАМЫЗ'),
                          SizedBox(height: 10),
                          Text('ИП ЖУМАШЕВ ЧИНГИС ЕРЖАНОВИЧ'),
                          Text('ИП Жумашев Чингис (Алматы, Мкр. Аксай 5, 25)'),
                          SizedBox(height: 10),
                          Text('ПРЕДЛАГАЕМ ВАМ ОПЛАТУ ЧЕРЕЗ QR-КОД'),
                          SizedBox(height: 10),
                          Text(
                            'Маңызды! Егер кофехана қызметкері жеке нөмірге аудару арқылы төлеуді ұсынса, бізге 8 771 456 07 20 хабарлаңыз',
                            textAlign: TextAlign.center,
                          ),
                          Text(
                            'Важно! Если персонал кофейни предложил оплату переводом на личный номер, сообщите нам на 8 771 456 07 20.',
                            textAlign: TextAlign.center,
                          ),
                        ],
                      ),
                      actions: [
                        TextButton(
                          onPressed: () => Navigator.pop(context),
                          child: Text('Жабу'),
                        ),
                      ],
                    ),
                  );
                },
                style: ElevatedButton.styleFrom(
                  backgroundColor: Colors.brown,
                  shape: RoundedRectangleBorder(
                    borderRadius: BorderRadius.circular(10),
                  ),
                ),
                child: Text('Сатып алу', style: TextStyle(color: Colors.white)),
              ),
            ),
          );
        },
      ),
    );
  }
}

class BonusScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.brown,
        title: Text('Bonus Offer', style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold, color: Colors.white)),
        centerTitle: true,
      ),
      body: Center(
        child: Text(
          'Coffee 10% OFF!',
          style: TextStyle(fontSize: 30, fontWeight: FontWeight.bold, color: Colors.brown),
        ),
      ),
    );
  }
}

# Menin-algashki-kodim
# Menin-en-algashki-kodim
